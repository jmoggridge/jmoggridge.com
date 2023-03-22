---
title: "Scrape a table from Wikipedia using R"
subtitle: "...without knowing anything about xml or css"
author: "Jason A. Moggridge"
date: '2022-08-26'
slug: []
excerpt: "Easy web scraping in R with tidyverse and the awesome rvest package"
draft: False
categories:
  - Coding
tags:
  - R
  - Tutorial
---




----

I want to get the data from the table on [this page](https://en.wikipedia.org/wiki/List_of_academic_publishers_by_preprint_policy) but copy/paste isn't working well and I just want the data *now*, I've got a ton of work to do! 

---

#### Setup



I use the `tidyverse` and `rvest` packages for this task.


```r
# install.packages(c('tidyverse', 'rvest'))
library(tidyverse)
library(rvest)

# This is our url
my_url <- "https://en.wikipedia.org/wiki/List_of_academic_publishers_by_preprint_policy"
```

#### Getting data

To get the table: `read_html()` gets the entire html content of the webpage; `html_node()` extracts the first table; then `html_table()` parses that element into an R data.frame that is easy to work with.


```r
(
  my_table <- 
    my_url |> 
    rvest::read_html() |>
    rvest::html_node('table') |> 
    rvest::html_table()
)
```

```
## # A tibble: 69 × 5
##    Publisher                                      Restr…¹ Restr…² Restr…³ Source
##    <chr>                                          <chr>   <chr>   <chr>   <chr> 
##  1 Publisher                                      Locati… Version License Source
##  2 American Association for the Advancement of S… Not-fo… Unrest… Unrest… [2]   
##  3 American Association for Cancer Research       Unrest… Must n… Unrest… [3]   
##  4 American Association for Physics in Medicine   Non-co… Unrest… Unrest… [4]   
##  5 American Chemical Society                      Unrest… Unrest… Unrest… [5]   
##  6 Association for Computing Machinery            Non-co… Unrest… Unrest… [6]   
##  7 American Geophysical Union                     Unrest… Unrest… Unrest… [7]   
##  8 American Heart Association                     Unrest… Versio… Unrest… [8]   
##  9 American Institute of Physics (AIP Publishing) Unrest… Unrest… Unrest… [9]   
## 10 American Institute of Aeronautics and Astrona… Unrest… Unrest… Unrest… [10]  
## # … with 59 more rows, and abbreviated variable names ¹​Restrictions,
## #   ²​Restrictions, ³​Restrictions
```

#### Cleanup

And we're done! Just kidding, the parser had a bit of trouble with the double header rows, where the three columns `Location`, `Version`, and `License` were grouped under `Restriction`. Currently, those three columns are named `Restriction`; that's not good - we need unique names to differentiate them.

To fix this, we'll just use the first row of the table to set the column names and then drop the first row from the table with `slice()`.


```r
(
  fixed_table <- 
    my_table |> 
    rlang::set_names(my_table[1,]) |>
    dplyr::slice(-1)
)
```

```
## # A tibble: 68 × 5
##    Publisher                                      Locat…¹ Version License Source
##    <chr>                                          <chr>   <chr>   <chr>   <chr> 
##  1 American Association for the Advancement of S… Not-fo… Unrest… Unrest… [2]   
##  2 American Association for Cancer Research       Unrest… Must n… Unrest… [3]   
##  3 American Association for Physics in Medicine   Non-co… Unrest… Unrest… [4]   
##  4 American Chemical Society                      Unrest… Unrest… Unrest… [5]   
##  5 Association for Computing Machinery            Non-co… Unrest… Unrest… [6]   
##  6 American Geophysical Union                     Unrest… Unrest… Unrest… [7]   
##  7 American Heart Association                     Unrest… Versio… Unrest… [8]   
##  8 American Institute of Physics (AIP Publishing) Unrest… Unrest… Unrest… [9]   
##  9 American Institute of Aeronautics and Astrona… Unrest… Unrest… Unrest… [10]  
## 10 American Physical Society                      Unrest… Unrest… Unrest… [11]  
## # … with 58 more rows, and abbreviated variable name ¹​Location
```

Before I save this data, I'll drop the `source` column (I didn't scrape the links for those anyway) and I'll make the names lower snake-case with `janitor::clean_names()` since I like having a consistent style for column names.


```r
(
  preprint_policy <- 
    fixed_table |> 
    select(-Source) |> 
    janitor::clean_names()
)
```

```
## # A tibble: 68 × 4
##    publisher                                           location  version license
##    <chr>                                               <chr>     <chr>   <chr>  
##  1 American Association for the Advancement of Science Not-for-… Unrest… Unrest…
##  2 American Association for Cancer Research            Unrestri… Must n… Unrest…
##  3 American Association for Physics in Medicine        Non-comm… Unrest… Unrest…
##  4 American Chemical Society                           Unrestri… Unrest… Unrest…
##  5 Association for Computing Machinery                 Non-comm… Unrest… Unrest…
##  6 American Geophysical Union                          Unrestri… Unrest… Unrest…
##  7 American Heart Association                          Unrestri… Versio… Unrest…
##  8 American Institute of Physics (AIP Publishing)      Unrestri… Unrest… Unrest…
##  9 American Institute of Aeronautics and Astronautics  Unrestri… Unrest… Unrest…
## 10 American Physical Society                           Unrestri… Unrest… Unrest…
## # … with 58 more rows
```

This looks good now so I'll save the data as a comma-separated values (.csv) for later use.


```r
readr::write_csv(preprint_policy, 'data/preprint_policy.csv')
```

-----

This was a really simple example and there are certainly more challenging web-scraping scenarios that require targeting a specific table(s) or have other obstacles in parsing. If this simple script solves your problem though, I don't think you'll find a quicker and easy way to grab a table from the web.

-----
