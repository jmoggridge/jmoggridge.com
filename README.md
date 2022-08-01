# jmoggridge.com 

*(blogdown-hugo-apero blog website)*

find useful docs here:

https://www.apreshill.com/blog/2019-02-spoonful-netlify-toml/


-----

## Setup

### Init

Do something like this to init a similar project

```
install.packages("blogdown")
blogdown::install_hugo()
blogdown::hugo_version()
blogdown::new_site(theme = "hugo-apero/hugo-apero", 
           format = "toml",
           sample = FALSE,
           empty_dirs = TRUE)
```

### Dev

Use `blogdown::serve_site()` to serve the site locally for development and  `blogdown::stop_server()` to stop the server.

`blogdown::check_config()`

### Deploy

**Don't you dare use `build site`** on this project, or you will regret all the generated files; Netlify (or whatever cdn) can build the site at deploy time. I set up CI/CD through github and netlify, such that the build is performed whenever there are pushes to the 'main' branch.

## Where to edit the blog theme

**Edit* the config.toml file for top-level settings

## Where to edit the blog content

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

### How to create a new post

First:

Then:

Finally:


-----
