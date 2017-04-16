---
title: Build a site like this using Blogdown and Github
author: Sheng
date: '2017-04-16'
slug: ''
categories: ["r"]
tags: ["r"]
---

[Blogdown](https://github.com/rstudio/blogdown) is a R package that generates static websites using [R Markdown](http://rmarkdown.rstudio.com) and [Hugo](https://gohugo.io). As a R user myself I already R Markdown to generate reproducible reports, so when I want to build a personal site I quickly adopted this. 
Here I will cover how I build this site and get it on github. 

## Getting started
First you need to install [R](https://cran.r-project.org) and  [RStudio](https://www.rstudio.com). Then you can install [devtools](https://cran.r-project.org/web/packages/devtools/index.html) and blogdown by
putting these in the R console inside RStudio:
```
install.packages("devtools")
devtools::install_github('rstudio/blogdown')
```

## Get your github repo ready
In your github, make a repo named `blog`, and do NOT initialized it with readme. In RStudio, create a new project by File -> New Project -> Version -> Git, put your `blog` repo URL in the box, name your local directory and select the path. Hit create Project button.

## Build the site
Your RStudio should automatically set its working directory properly. You can now initialize a site with:
```
blogdown::new_site(theme = "gcushen/hugo-academic")
```
The `theme` parameter is optional here, and you can look for more themes in the [hugo gallary](http://themes.gohugo.io). However, I found that things may get messy if you choose to install/change themes later, so I would suggest picking a theme before you start and stick with it. The [hugo-academic](https://themes.gohugo.io/academic/) theme suits my needs very well.

Now you have a working local site, and a preview is available in the Viewer pane. 


## Customizing settings
Open `config.toml` and add the following line:
```
publishDir = "docs"
```
This is to make sure the html files get generated into the `docs` directory, and it'll make things easier to get it hosted on github. If you choose to use the `hugo-academic` theme, you also need to set the `baseurl`:
```
baseurl = "https://YOUR-USER-NAME.github.io/blog/"
```
There is a ton of other parameters in `config.toml`, but they should be self-explanatory once you get the site going.

You can now build your site with
```
blogdown::build_site(local = FALSE, method = "html_encoded")
```
and commit it to your github repo using either the built-in version control tool or any other way you like.

Go to your github repo, settings, and choose `master branch /docs folder` under GitHub Pages panel. Save it, and your blog should be able to go at `https://YOUR-USER-NAME.github.io/blog/` !

## Adding redirection from personal page
If you want your blog to be available at `https://YOUR-USER-NAME.github.io/`, there is another few steps to go. Head over to github again and create a repo named `YOUR-USER-NAME.github.io`, and clone it into any local copy. 

Add a `index.html` that redirects the visitor to `https://YOUR-USER-NAME.github.io/blog/`. Here is my (shamelessly copied) version:
```
<!DOCTYPE HTML>
<html lang="en-US">
    <head>
        <meta charset="UTF-8">
        <meta http-equiv="refresh" content="1; url=https://sfeng77.github.io/blog/">
        <script type="text/javascript">
            window.location.href = "https://sfeng77.github.io/blog/"
        </script>
        <title>Page Redirection</title>
    </head>
    <body>
        <!-- Note: don't tell people to `click` the link, just tell them that it is a link. -->
        If you are not redirected automatically, follow this <a href='https://sfeng77.github.io/blog/'>link to my blog</a>.
    </body>
</html>
```
Obviously you want to change all the `sfeng77` to your user name in there if you don't want all your readers redirected to my blog. Commit and push it, and it should work out in a little bit.  

## Patience is a virtue
Sometimes it'll take a while before the changes are reflected on github pages.

## Adding/Changing/Deleting content
You can add content by adding markdown or R Makrdown into the sub-directories in `content` directory. There are a bunch of examples that you can follow. You can also use 
```
blogdown::new_post("POST-TITLE")
```

The academic themed homepage is built of widgets, and you can remove the widgets you don't like by deleting the corresponding `md` file from `content/home/`. If you want to delete a specific post, just remove it from `content/post`. The images you want to reference should be in `static/img` directory.   

After you've made the changes, **MAKE SURE** you build the site and push it to github. Have fun with it! 


## Some more Reference
This is where I learned to get github pages working:
http://applyr.blogspot.com/2017/01/blogging-about-r-from-r-studio.html

A (work-in-progress) reference of blogdown:
https://bookdown.org/yihui/blogdown/

A reference of the academic theme:
https://georgecushen.com/create-your-website-with-hugo/




