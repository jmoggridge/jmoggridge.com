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

**Don't use build site**

Netlify can build the site at deploy


  $
├── R
│   ├── build.R
│   └── build2.R
├── README.md
├── archetypes
├── blogdown_hugoapero.Rproj
├── config.toml
├── content
│   ├── _index.md
│   ├── about
│   │   ├── _index.md
│   │   ├── header
│   │   │   └── index.md
│   │   ├── main
│   │   │   └── index.md
│   │   └── sidebar
│   │       ├── audio.m4a
│   │       ├── avatar.jpg
│   │       └── index.md
│   ├── blog
│   │   ├── _index.md
│   │   ├── built-in-contact-form
│   │   │   ├── built-in-contact-form-featured.png
│   │   │   ├── built-in-contact-form-screenshot.png
│   │   │   ├── formspree-logo.png
│   │   │   └── index.md
│   │   ├── color-themes
│   │   │   ├── color-featured.png
│   │   │   ├── index.md
│   │   │   ├── peach.png
│   │   │   └── tachyons-logo-script.png
│   │   ├── css-grid-scaffold
│   │   │   ├── css-grid-cover.png
│   │   │   ├── css-grid-featured.png
│   │   │   └── index.md
│   │   ├── evergreen
│   │   │   ├── featured.jpg
│   │   │   └── index.md
│   │   ├── fonts
│   │   │   ├── font-assets-css.png
│   │   │   ├── font-config.png
│   │   │   ├── font-static-files.png
│   │   │   ├── fonts-featured.png
│   │   │   ├── hachi-font.png
│   │   │   ├── index.md
│   │   │   ├── isaac-font.png
│   │   │   ├── system-font.png
│   │   │   └── tachyons-logo-script.png
│   │   ├── rmarkdown
│   │   │   ├── index.Rmarkdown
│   │   │   ├── index.markdown
│   │   │   └── index_files
│   │   │       └── figure-html
│   │   │           ├── unnamed-chunk-1-1.png
│   │   │           ├── unnamed-chunk-2-1.png
│   │   │           └── unnamed-chunk-3-1.png
│   │   ├── seedling
│   │   │   ├── featured.jpg
│   │   │   └── index.md
│   │   ├── sidebar-listing.jpg
│   │   ├── social
│   │   │   ├── featured.jpg
│   │   │   └── index.md
│   │   └── spoonful-series
│   │       ├── 01-spoonful.md
│   │       ├── 02-spoonful
│   │       │   ├── index.md
│   │       │   └── sidebar-inverse.jpg
│   │       ├── 03-spoonful
│   │       │   ├── featured-photo.jpg
│   │       │   ├── index.Rmarkdown
│   │       │   └── index.markdown
│   │       ├── _index.md
│   │       └── sidebar-featured.jpg
│   ├── collection
│   │   ├── _index.md
│   │   ├── day01
│   │   │   ├── 01-github
│   │   │   │   └── index.md
│   │   │   ├── 02-postcards
│   │   │   │   └── index.md
│   │   │   ├── 03-distill
│   │   │   │   ├── index.md
│   │   │   │   ├── rproj-diff.png
│   │   │   │   └── rproj-git.png
│   │   │   ├── _index.md
│   │   │   └── featured.jpg
│   │   ├── day02
│   │   │   ├── 01-netlify
│   │   │   │   └── index.md
│   │   │   ├── 02-blogdown
│   │   │   │   └── index.md
│   │   │   ├── 03-blogdown
│   │   │   │   └── index.md
│   │   │   ├── _index.md
│   │   │   └── featured.jpg
│   │   ├── featured-sidebar.jpg
│   │   └── prework
│   │       ├── featured.jpg
│   │       └── index.md
│   ├── contributors.md
│   ├── elements
│   │   └── index.html
│   ├── form
│   │   └── contact.md
│   ├── license.md
│   ├── project
│   │   ├── _index.md
│   │   ├── bakeoff
│   │   │   ├── built-in-contact-form-screenshot.png
│   │   │   ├── built-in-contact-form-thumbnail.png
│   │   │   ├── featured-hex.png
│   │   │   ├── formspree-logo.png
│   │   │   └── index.md
│   │   ├── giraffes
│   │   │   ├── featured-hex.png
│   │   │   ├── index.md
│   │   │   ├── tachyons-logo-script.png
│   │   │   └── tachyons-thumbnail.png
│   │   ├── penguins
│   │   │   ├── css-grid-cover.png
│   │   │   ├── css-grid-thumbnail.png
│   │   │   ├── featured-hex.png
│   │   │   └── index.md
│   │   └── sidebar-listing.jpg
│   └── talk
│       ├── _index.md
│       ├── campfire
│       │   ├── featured.jpg
│       │   └── index.md
│       ├── second-seedling
│       │   ├── featured.jpg
│       │   └── index.md
│       ├── seedling
│       │   ├── featured.jpg
│       │   └── index.md
│       └── sidebar-listing.jpg
├── data
│   └── ads
│       └── formspree.yaml
├── index.Rmd
├── layouts
│   └── shortcodes
│       └── blogdown
│           └── postref.html
├── netlify.toml
├── public
│   ├── 404.html
│   ├── about
│   │   ├── index.html
│   │   ├── index.xml
│   │   └── sidebar
│   │       ├── audio.m4a
│   │       └── avatar.jpg
│   ├── blog
│   │   ├── built-in-contact-form
│   │   │   ├── built-in-contact-form-featured.png
│   │   │   ├── built-in-contact-form-screenshot.png
│   │   │   ├── formspree-logo.png
│   │   │   └── index.html
│   │   ├── color-themes
│   │   │   ├── color-featured.png
│   │   │   ├── index.html
│   │   │   ├── peach.png
│   │   │   └── tachyons-logo-script.png
│   │   ├── css-grid-scaffold
│   │   │   ├── css-grid-cover.png
│   │   │   ├── css-grid-featured.png
│   │   │   └── index.html
│   │   ├── evergreen
│   │   │   ├── featured.jpg
│   │   │   └── index.html
│   │   │   ├── index.html
│   │   │   └── index.xml
│   │   └── workshop
│   │       ├── index.html
│   │       └── index.xml
│   ├── collection
│   │   ├── day01
│   │   │   ├── 01-github
│   │   │   │   └── index.html
│   │   │   ├── 02-postcards
│   │   │   │   └── index.html
│   │   │   ├── 03-distill
│   │   │   │   ├── index.html
│   │   │   │   ├── rproj-diff.png
│   │   │   │   └── rproj-git.png
│   │   │   ├── featured.jpg
│   │   │   ├── index.html
│   │   │   └── index.xml
│   │   ├── day02
│   │   │   ├── 01-netlify
│   │   │   │   └── index.html
│   │   │   ├── 02-blogdown
│   │   │   │   └── index.html
│   │   │   ├── 03-blogdown
│   │   │   │   └── index.html
│   │   │   ├── featured.jpg
│   │   │   ├── index.html
│   │   │   └── index.xml
│   │   ├── featured-sidebar.jpg
│   │   ├── index.html
│   │   ├── index.xml
─ Fraunces9pt-SemiBold.woff2
│   │   ├── Fraunces9pt-SemiBoldItalic.woff2
│   │   ├── Fraunces9pt-Thin.woff2
│   │   ├── Fraunces9pt-ThinItalic.woff2
│   │   ├── Fraunces9ptSoft-Black.woff2
│   │   ├── Fraunces9ptSoft-BlackItalic.woff2
│   │   ├── Fraunces9ptSoft-Bold.woff2
│   │   ├── Fraunces9ptSoft-BoldItalic.woff2
│   │   ├── Fraunces9ptSoft-Italic.woff2
│   │   ├── Fraunces9ptSoft-Light.woff2
│   │   ├── Fraunces9ptSoft-LightItalic.woff2
│   │   ├── Fraunces9ptSoft-Regular.woff2
│   │   ├── Fraunces9ptSoft-SemiBold.woff2
│   │   ├── Fraunces9ptSoft-SemiBoldItalic.woff2
│   │   ├── Fraunces9ptSoft-Thin.woff2
│   │   ├── Fraunces9ptSoft-ThinItalic.woff2
│   │   ├── Fraunces9ptSuperSoft-Black.woff2
│   │   ├── Fraunces9ptSuperSoft-BlackItalic.woff2
│   │   ├── Fraunces9ptSuperSoft-Bold.woff2
│   │   ├── Fraunces9ptSuperSoft-BoldItalic.woff2
│   │   ├── Fraunces9ptSuperSoft-Italic.woff2
│   │   ├── Fraunces9ptSuperSoft-Light.woff2
│   │   ├── Fraunces9ptSuperSoft-LightItalic.woff2
│   │   ├── Fraunces9ptSuperSoft-Regular.woff2
│   │   ├── Fraunces9ptSuperSoft-SemiBold.woff2
│   │   ├── Fraunces9ptSuperSoft-SemiBoldItalic.woff2
│   │   ├── Fraunces9ptSuperSoft-Thin.woff2
│   │   ├── Fraunces9ptSuperSoft-ThinItalic.woff2
│   │   ├── Metropolis-Light.woff
││   │   │   └── index.xml
│   │   ├── index.html
│   │   └── index.xml
│   ├── sitemap.xml
│   ├── style.main.min.5477c20f89738a32763391bbc2f43dbdfc2db0e7faba550c86cac92c99efa6b6.css
│   ├── style.main.min.a2eeb21b35249ea1cba62c43c3c30fd413c04f5edf10772bf2a2fc68006cf988.css
│   ├── tags
│   │   ├── hugo-site
│   │   │   ├── index.html
│   │   │   └── index.xml
│   │   ├── index.html
│   │   ├── index.xml
│   │   └── style
│   │       ├── index.html
│   │       └── index.xml
│   ├── talk
│   │   ├── campfire
│   │   │   ├── featured.jpg
│   │   │   └── index.html
│   │   ├── index.html
│   │   ├── index.xml
│   │   ├── page
│   │   │   └── 1
│   │   │       └── index.html
│   │   ├── second-seedling
│   │   │   ├── featured.jpg
│   │   │   └── index.html
│   │   ├── seedling
│   │   │   ├── featured.jpg
│   │   │   └── index.html
│   │   └── sidebar-listing.jpg
│   └── webfonts
│       ├── academicons.eot
│       ├── academicons.svg
│       ├── academicons.ttf
│       ├── academicons.woff
│       ├── fa-brands-400.eot
│       ├── fa-brands-400.svg
│       ├── fa-brands-400.ttf
│       ├── fa-brands-400.woff
│       ├── fa-brands-400.woff2
│       ├── fa-regular-400.eot
│       ├── fa-regular-400.svg
│       ├── fa-regular-400.ttf
│       ├── fa-regular-400.woff
│       ├── fa-regular-400.woff2
│       ├── fa-solid-900.eot
│       ├── fa-solid-900.svg
│       ├── fa-solid-900.ttf
│       ├── fa-solid-900.woff
│       └── fa-solid-900.woff2
├── resources
│   └── _gen
│       ├── assets
│       │   └── scss
│       │       ├── scaffold.scss_545d7c693f5b5f74d129019eb310e64e.content
│       │       └── scaffold.scss_545d7c693f5b5f74d129019eb310e64e.json
│       └── images
├── static
│   ├── favicon_io
│   │   ├── about.txt
│   │   ├── android-chrome-192x192.png
│   │   ├── android-chrome-512x512.png
│   │   ├── apple-touch-icon.png
│   │   ├── favicon-16x16.png
│   │   ├── favicon-32x32.png
│   │   └── site.webmanifest
│   ├── favicon_io.zip
│   └── img
│       ├── favicon.ico
│       ├── friends.png
│       ├── mito.png
│       ├── nudi.jpg
│       ├── nudi.png
│       ├── nudi2.png
│       ├── nudi3.png
│       └── nudi4.png
└── themes
    └── hugo-apero
        ├── LICENSE.md
        ├── README.md
        ├── archetypes
        │   ├── blog
        │   │   ├── featured.jpg
        │   │   └── index.md
        │   ├── default.md
        │   ├── form.md
        │   ├── page.md
        │   ├── project
        │   │   ├── featured.jpg
        │   │   └── index.md
        │   └── talk
        │       ├── featured.jpg
        │       └── index.md
        ├── assets
        │   ├── academicons
        │   │   ├── academicons.scss
        │   │   └── package.json
        │   ├── base.scss
        │   ├── custom-fonts.scss
        │   ├── custom.scss
        │   ├── fontawesome-free-5.15.1-web
        │   │   └── scss
        │   │       ├── _animated.scss
        │   │       ├── _bordered-pulled.scss
        │   │       ├── _core.scss
        │   │       ├── _fixed-width.scss
        │   │       ├── _icons.scss
        │   │       ├── _larger.scss
        │   │       ├── _list.scss
        │   │       ├── _mixins.scss
        │   │       ├── _rotated-flipped.scss
        │   │       ├── _screen-reader.scss
        │   │       ├── _shims.scss
        │   │       ├── _stacked.scss
        │   │       ├── _variables.scss
        │   │       ├── brands.scss
        │   │       ├── fontawesome.scss
        │   │       ├── regular.scss
        │   │       ├── solid.scss
        │   │       └── v4-shims.scss
        │   ├── headroom.scss
        │   ├── hex-colors.scss
        │   ├── js
        │   │   ├── headroom.js
        │   │   ├── main.js
        │   │   └── panelset.js
        │   ├── jsconfig.json
        │   ├── named-colors.scss
        │   ├── .scss
        │   │   ├── _max-widths.scss
        │   │   ├── _module-template.scss
        │   │   ├── _negative-margins.scss
        │   │   ├── _nested.scss
        │   │   ├── _normalize.scss
        │   │   ├── _opacity.scss
        │   │   ├── _outlines.scss
        │   │   ├── _overflow.scss
        │   │   ├── _position.scss
        │   │   ├── _rotations.scss
        │   │   ├── _skins-pseudo.scss
        │   │   ├── _skins.scss
        │   │   ├── _spacing.scss
        │   │   ├── _styles.scss
        │   │   ├── _tables.scss
        │   │   ├── _text-align.scss
        │   │   ├── _text-decoration.scss
        │   │   ├── _text-transform.scss
        │   │   ├── _type-scale.scss
        │   │   ├── _typography.scss
        │   │   ├── _utilities.scss
        │   │   ├── _variables.scss
        │   │   ├── _vertical-align.scss
        │   │   ├── _visibility.scss
        │   │   ├── _white-space.scss
        │   │   ├── _widths.scss
        │   │   ├── _word-break.scss
        │   │   └── _z-index.scss
        │   ├── tachyons.scss
        │   └── theme
        │       ├── forest.scss
        │       ├── grayscale.scss
        │       ├── peach.scss
        │       ├── plum.scss
        │       ├── poppy.scss
        │       ├── set-theme.scss
        │       ├── sky.scss
        │       ├── violet.scss
        │       └── water.scss
        ├── exampleSite
        │   ├── config.toml
        │   ├── content
        │   │   ├── _index.md
        │   │   ├── about
        │   │   │   ├── _index.md
        │   │   │   ├── header
        │   │   │   │   └── index.md
        │   │   │   ├── main
        │   │   │   │   └── index.md
        │   │   │   └── sidebar
        │   │   │       ├── audio.m4a
        │   │   │       ├── avatar.jpg
        │   │   │       └── index.md
        │   │   ├── blog
        │   │   │   ├── _index.md
        │   │   │   ├── built-in-contact-form
        │   │   │       ├── 03-spoonful
        │   │   │       │   ├── featured-photo.jpg
        │   │   │       │   ├── index.Rmarkdown
        │   │   │       │   └── index.markdown
        │   │   │       ├── _index.md
        │   │   │       └── sidebar-featured.jpg
        │   │   ├── collection
        │   │   │   ├── _index.md
        │   │   │   ├── day01
        │   │   │   │   ├── 01-github
        │   │   │   │   │   └── index.md
        │   │   │   │   ├── 02-postcards
        │   │   │   │   │   └── index.md
        │   │   │   │   ├── 03-distill
        │   │   │   │   │   ├── index.md
        │   │   │   │   │   ├── rproj-diff.png
        │   │   │   │   │   └── rproj-git.png
        │   │   │   │   ├── _index.md
        │   │   │   │   └── featured.jpg
        │   │   │   ├── day02
        │   │   │   │   ├── 01-netlify
        │   │   │   │   │   └── index.md
        │   │   │   │   ├── 02-blogdown
        │   │   │   │   │   └── index.md
        │   │   │   │   ├── 03-blogdown
        │   │   │   │   │   └── index.md
        │   │   │   │   ├── _index.md
        │   │   │   │   └── featured.jpg
        │   │   │   ├── featured-sidebar.jpg
        │   │   │   └── prework
        │   │   │       ├── featured.jpg
        │   │   │       └── index.md
        │   │   ├── contributors.md
        │   │   ├── elements
        │   │   │   └── index.html
        │   │   ├── form
        │   │   │   └── contact.md
        │   │   ├── license.md
        │   │   ├── project
        │   │   │   ├── _index.md
        │   │   │   ├── bakeoff
        │   │   │   │   ├── built-in-contact-form-screenshot.png
        │   │   │   │   ├── built-in-contact-form-thumbnail.png
        │   │   │   │   ├── featured-hex.png
        │   │   │   │   ├── formspree-logo.png
        │   │   │   │   └── index.md
        │   │   │   ├── giraffes
        │   │   │   │   ├── featured-hex.png
        │   │   │   │   ├── index.md
        │   │   │   │   ├── tachyons-logo-script.png
        │   │   │   │   └── tachyons-thumbnail.png
        │   │   │   ├── penguins
        │   │   │   │   ├── css-grid-cover.png
        │   │   │   │   ├── css-grid-thumbnail.png
        │   │   │   │   ├── featured-hex.png
        │   │   │   │   └── index.md
        │   │   │   └── sidebar-listing.jpg
        │   │   └── talk
        │   │       ├── _index.md
        │   │       ├── campfire
        │   │       │   ├── featured.jpg
        │   │       │   └── index.md
        │   │       ├── second-seedling
        │   │       │   ├── featured.jpg
        │   │       │   └── index.md
        │   │       ├── seedling
        │   │       │   ├── featured.jpg
        │   │       │   └── index.md
        │   │       └── sidebar-listing.jpg
        │   ├── data
        │   │   └── ads
        │   │       └── formspree.yaml
        │   └── layouts
        │       └── shortcodes
        │           └── blogdown
        │               └── postref.html
        ├── layouts
        │   ├── 404.html
        │   ├── _default
        │   │   ├── _markup
        │   │   │   ├── render-heading.html
        │   │   │   └── render-link.html
        │   │   ├── baseof.html
        │   │   ├── list.html
        │   │   └── single.html
        │   ├── about
        │   │   └── list.html
        │   ├── blog
        │   │   ├── list-grid.html
        │   │   ├── list-sidebar.html
        │   │   ├── single-series.html
        │   │   └── single-sidebar.html
        │   ├── collection
        │   │   ├── list-sidebar.html
        │   │   ├── list.html
        │   │   └── single-series.html
        │   ├── form
        │   │   ├── split-left.html
        │   │   └── split-right.html
        │   ├── index.html
        │   ├── page
        │   │   ├── standard.html
        │   │   └── wide-body.html
        │   ├── partials
        │   │   ├── footer.html
        │   │   ├── head.html
        │   │   ├── header.html
        │   │   ├── meta.html
        │   │   └── shared
        │   │       ├── about-links.html
        │   │       ├── attribution.html
        │   │       ├── breadcrumb.html
        │   │       ├── btn-links.html
        │   │       ├── comments.html
        │   │       ├── contact-form.html
        │   │       ├── date-range.html
        │   │       ├── event-details.html
        │   │       ├── list-pagination.html
        │   │       ├── math-preprocess.html
        │   │       ├── math-render-katex.html
        │   │       ├── math-render-mathjax.html
        │   │       ├── post-details.html
        │   │       ├── post-pagination.html
        │   │       ├── section-sidebar.html
        │   │       ├── series-sidebar.html
        │   │       ├── sidebar
        │   │       │   ├── sidebar-adunit.html
        │   │       │   ├── sidebar-header.html
        │   │       │   ├── sidebar-image.html
        │   │       │   └── sidebar-link.html
        │   │       ├── sidebar-scaffold.html
        │   │       ├── social-links.html
        │   │       ├── summary-compact.html
        │   │       ├── summary-grid.html
        │   │       ├── summary-li.html
        │   │       ├── summary-section.html
        │   │       ├── summary.html
        │   │       └── time-range.html
        │   ├── project
        │   │   ├── list-grid.html
        │   │   ├── list-sidebar.html
        │   │   └── single-sidebar.html
        │   ├── shortcodes
        │   │   ├── blogdown
        │   │   │   └── postref.html
        │   │   ├── here.html
        │   │   ├── panel.html
        │   │   └── panelset.html
        │   ├── talk
        │   │   ├── list-sidebar.html
        │   │   ├── list.html
        │   │   └── single.html
        │   └── taxonomy
        │       ├── taxonomy.html
        │       └── term.html
        ├── netlify.toml
        ├── static
        │   ├── fonts
  │   ├── Fraunces9ptSoft-Bold.woff2
        │   │   ├── Fraunces9ptSoft-BoldItalic.woff2
        │   │   ├── Fraunces9ptSoft-Italic.woff2
        │   │   ├── Fraunces9ptSoft-Light.woff2
        │   │   ├── Fraunces9ptSoft-LightItalic.woff2
        │   │   ├── Fraunces9ptSoft-Regular.woff2
        │   │   ├── Fraunces9ptSoft-SemiBold.woff2
        │   │   ├── Fraunces9ptSoft-SemiBoldItalic.woff2
        │   │   ├── Fraunces9ptSoft-Thin.woff2
        │   │   ├── Fraunces9ptSoft-ThinItalic.woff2
        │   │   ├── Fraunces9ptSuperSoft-Black.woff2
        │   │   ├── Fraunces9ptSuperSoft-BlackItalic.woff2
        │   │   ├── Fraunces9ptSuperSoft-Bold.woff2
        │   │   ├── Fraunces9ptSuperSoft-BoldItalic.woff2
        │   │   ├── Fraunces9ptSuperSoft-Italic.woff2
        │   │   ├── Fraunces9ptSuperSoft-Light.woff2
        │   │   ├── Fraunces9ptSuperSoft-LightItalic.woff2
        │   │   ├── Fraunces9ptSuperSoft-Regular.woff2
        │   │   ├── Fraunces9ptSuperSoft-SemiBold.woff2
        │   │   ├── Fraunces9ptSuperSoft-SemiBoldItalic.woff2
        │   │   ├── Fraunces9ptSuperSoft-Thin.woff2
        │   │   ├── Fraunces9ptSuperSoft-ThinItalic.woff2
        │   │   ├── Metropolis-Light.woff
        │   │   ├── Metropolis-Light.woff2
        │   │   ├── Metropolis-LightItalic.woff
        │   │   ├── Metropolis-LightItalic.woff2
        │   │   ├── bitter-v16-latin-300.woff
        │   │   ├── bitter-v16-latin-300.woff2
        │   │   ├── bitter-v16-latin-300italic.woff
        │   │   ├── bitter-v16-latin-300italic.woff2
        │   │   ├── eb-garamond-v14-latin-600.woff
        │   │   ├── eb-garamond-v14-latin-600.woff2
        │   │   ├── eb-garamond-v14-latin-600italic.woff
        │   │   ├── eb-garamond-v14-latin-600italic.woff2
        │   │   ├── eb-garamond-v14-latin-italic.woff
        │   │   ├── eb-garamond-v14-latin-italic.woff2
        │   │   ├── eb-garamond-v14-latin-regular.woff
        │   │   └── eb-garamond-v14-latin-regular.woff2
        │   ├── img
        │   │   ├── arbre.jpg
        │   │   ├── avatar-right.jpg
        │   │   ├── avatar.jpg
        │   │   ├── barbier.jpg
        │   │   ├── blogophonic-mark-dark.png
        │   │   ├── favicon.ico
        │   │   ├── papillons.jpg
        │   │   ├── revoir.jpg
        │   │   ├── screenshot.png
        │   │   └── unicorn-megaphone.png
        │   └── webfonts
