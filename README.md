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

You can use build tools and `rmarkdown::clean_site(preview = FALSE)` to remove the generated files from /public. Netlify (or whatever cdn) can build the site at deploy time too but it's hard to troubleshoot that way. I set up CI/CD through github and netlify, such that the build is performed whenever there are pushes to the 'main' branch.

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

Easy to create: `blogdown:::new_post_addin()`

Then write: Find and edit the .md or .rmd in `_/content/blog/<post>/`
    
Finally: Add a thumb image as `featured.png` in `_/content/blog/<post>/` 


-----
