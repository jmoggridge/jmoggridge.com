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
