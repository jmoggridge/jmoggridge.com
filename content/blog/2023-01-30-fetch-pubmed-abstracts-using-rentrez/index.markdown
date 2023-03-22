---
title: "Fetch Pubmed Abstracts Using Rentrez"
author: "Jason Moggridge"
date: '2023-01-30T16:41:40-08:00'
slug: []
draft: False
categories:
  - Coding
tags:
  - R
  - Tutorial
---


##

----

I want to search PubMed for abstracts related to some search term for a review...

---

#### Setup



I use `rentrez` to create requests to the NCBI API, while `tidyverse` helps me get the data into a tabular form, which will be easier to manipulate than a list of rentrez's `pubmed_record` objects.


```r
library(tidyverse)
library(rentrez)
```

#### Search 

Searching and fetching steps are separate. The first step is to use `rentrez::search()` on the pubmed database to find the articles matching your query. We set the `web_history` flag to `TRUE`, such that we will receive a response with a `web_history` token, which is like a receipt for the search results that were found.


```r
# do an initial search and get a web_history token for the results
hits <- rentrez::entrez_search(
  term =  '((artificial intelligence) OR (machine learning)) AND (malaria)', 
  db = 'pubmed',
  use_history = T)
```

The query  '((artificial intelligence) OR (machine learning)) AND (malaria)' returns many results, but less than 10,000, which appears to be the limit for a single request.


```r
(hits$count)
```

```
## [1] 419
```

Our web_history token allows us to access the results with our fetch call (instead of needing to provide all the ids!)


```r
(hits$web_history)
```

```
## Web history object (QueryKey = 1, WebEnv = MCID_63d86e0...)
```

#### Fetch

We can then provide the `web_history` value as a parameter for `rentrez::fetch()` to get the desired articles. We pipe the response into `parse_pubmed_xml()` to get the data into an R-friendly format. 


```r
# get results (capped at 1000 - need to do multiple requests for more)
res <- 
  rentrez::entrez_fetch(
    db = 'pubmed', 
    web_history = hits$web_history,
    rettype = 'xml',
    retmode = 'xml'
  ) |> 
  rentrez::parse_pubmed_xml()
```

If your search returns more than 10k results, you'll need to do multiple fetches while changing the `retmin` and `retmax` parameters to grab successive chunks of the search results...


```r
fetch_res <- function(retmin, retmax, token) {
  rentrez::entrez_fetch(
    db = 'pubmed', 
    web_history = token,
    rettype = 'xml',
    retmode = 'xml',
    retmin = retmin,
    retmax = retmax
  ) |> 
    rentrez::parse_pubmed_xml() |> 
    map( 
      ~tibble_row(
        title = pluck(.x, 'title'),
        year = pluck(.x, 'year'),
        abstract = pluck(.x, 'abstract') |> 
          paste0(collapse = '\n') |> 
          tolower(),
        doi = pluck(.x, 'doi'),
        pmid = pluck(.x, 'pmid'),
        authors = lst(pluck(.x, 'authors')),
      )
    ) |>
    bind_rows()
}

# do the initial search
cancer_hits <- rentrez::entrez_search(
  term =  'cancer', 
  db = 'pubmed',
  use_history = T)

# Lots of hits
cancer_hits$count
```

```
## [1] 4786776
```

```r
# setup indexing 
retmin <- seq(0, 10000, 10000)
retmax <- seq(10000, 20000, 10000)

# be patient (maybe add a progress bar!) 
df <- map2(.x = retmin, .y = retmax, 
     .f = ~fetch_res(.x, .y, token = cancer_hits$web_history))
```

#### Tidy

The objects that we get back after parsing can be organized into a tibble (or data.frame), which will be easier to work with. While we do this, we can combine the list of paragraphs for each abstract into a single character string using `paste0`, which will also make the analysis simpler.


```r
# rectangle data so it's easier to work with
df <- res |> 
  map( 
    ~tibble_row(
      title = pluck(.x, 'title'),
      year = pluck(.x, 'year'),
      abstract = pluck(.x, 'abstract') |> paste0(collapse = '\n') |> tolower(),
      doi = pluck(.x, 'doi'),
      pmid = pluck(.x, 'pmid'),
      authors = lst(pluck(.x, 'authors')),
    )) |>
  bind_rows()

glimpse(df)
```

```
## Rows: 419
## Columns: 6
## $ title    <chr> "Malaria absorption peaks acquired through the skin of patien…
## $ year     <chr> "2022", "2023", "2023", "2023", "2022", "2022", "2022", "2023…
## $ abstract <chr> "to eliminate malaria, scalable tools that are rapid, afforda…
## $ doi      <chr> "10.1093/pnasnexus/pgac272", "10.1186/s12936-023-04446-0", "1…
## $ pmid     <chr> "36712329", "36707822", "36653779", "36624386", "36567678", "…
## $ authors  <named list> <"Garcia, Gabriela A", "Kariyawasam, Tharanga N", "Lor…
```


#### Data mining

Now that the data is in handy tabular format, it should be (relatively) easy for you to do your analysis using R! For example, maybe you want to count how many articles contain a certain term...


```r
# can now do word searches through abstracts, like...
df |> 
  mutate(mentions_deeplearning = str_detect(abstract, 'deep learning')) |> 
  filter(mentions_deeplearning)
```

```
## # A tibble: 38 × 7
##    title                               year  abstr…¹ doi   pmid  authors menti…²
##    <chr>                               <chr> <chr>   <chr> <chr> <named> <lgl>  
##  1 Using transfer learning and dimens… 2023  "old m… 10.1… 3662… <chr>   TRUE   
##  2 Geographical classification of mal… 2022  "malar… 10.1… 3647… <chr>   TRUE   
##  3 Advances and challenges in automat… 2022  "malar… 10.3… 3645… <chr>   TRUE   
##  4 Application of machine and deep le… 2022  "machi… 10.1… 3637… <chr>   TRUE   
##  5 Predicting infectious disease for … 2022  "the c… 10.1… 3627… <chr>   TRUE   
##  6 Automated wide-field malaria paras… 2022  "diagn… 10.1… 3599… <chr>   TRUE   
##  7 An efficient model of residual bas… 2022  "malar… 10.1… 3596… <chr>   TRUE   
##  8 Prediction of malaria using deep l… 2022  "malar… 10.1… 3594… <chr>   TRUE   
##  9 Explainable Transformer-Based Deep… 2022  "malar… 10.3… 3574… <chr>   TRUE   
## 10 Barnacles Mating Optimizer with De… 2022  "biome… 10.1… 3569… <chr>   TRUE   
## # … with 28 more rows, and abbreviated variable names ¹​abstract,
## #   ²​mentions_deeplearning
```



Good luck!

-----
