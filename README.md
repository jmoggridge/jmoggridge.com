# blogdown_hugoapero


## Setup

```
install.packages("blogdown")
blogdown::install_hugo()
blogdown::hugo_version()
blogdown::new_site(theme = "hugo-apero/hugo-apero", 
           format = "toml",
           sample = FALSE,
           empty_dirs = TRUE)
`blogdown::serve_site()`
`blogdown::stop_server()`

```


**Edited* the .toml file

`blogdown::check_config()`

## First off

**Don't you fucking dare use `build site`** on this project, or you will regret all the generated files; Netlify (or whatever cdn) can build the site at deploy time.  


## How this blogdown-hugo-apero blog works

[](https://twitter.com/apreshill/status/1078494406301212672?s=20&t=wfHoNrrz9PbRhtIJWzHdbA)

An #rstats #blogdown file hierarchy cheatsheet:
    
    ├─ archetypes <- edit me! 
    ├─ config.toml <- edit me! 
    ├─ content <- edit me! 
    ├─ data <- edit me! 
    ├─ layouts <- edit me! 
    ├─ public <- ignore me!
    ├─ static <- use me! (png/pdf/csv/xls)
    ├─ themes <- don't touch!


