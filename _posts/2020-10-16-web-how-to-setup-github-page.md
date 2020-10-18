---
layout: post
title: "Jekyll and Hyde"
subtitle: "How to use Jekyll and Hydejack to create a blog site"
categories: coding
tags: web
comments: true
---

# Jekyll and Hyde: How to use Jekyll and Hydejack to create a blog site
## Why use Jekyll?

[GitHub Pages](https://pages.github.com/) is a great way to create a blog site.
The advantages are:

* **It is free:** If you have a github account, you can have one personal github page for free
 as long as the domain name is [github user id].github.io.

* **Maintained by github:** You don't have to worry about version control, building, deploying,
 and all the headaches with the website maintenance. All these are done by github.
  Did I mention that they are free?

* **Easy to setup:** GitHub uses [Jekyll](https://jekyllrb.com/) which transforms
[Markdown](https://en.wikipedia.org/wiki/Markdown) files which are basically plain text files into beautiful blogs.

## Which Jekyll theme to use?

The easiest way to setup a github page is to use one of the [Jekyll themes](http://jekyllthemes.org/).
A Jekyll theme is a style template that the users can customize. For choosing a theme, I had the requirements:

1. **Simple design:** I am a minimalist or at least I strive to be a minimalist so I hate any design that is overly complicated and flashy.
 I believe that the KISS (Keep It Simple Stupid) design principle is the best user experience. 

2. **Easy to customize:** Simplicity is the guiding principle, but it needs to be easy to customize
 and add necessary features later.

3. **Search function:** I have two other blogging sites that I still maintain for quite sometime and
I found that without search functionality, you cannot find the content you need.
 So search function is an absolute necessity.
 
Based on these requirements, I searched a few themes. Here were a few candidates:

1. [FastAI](https://github.com/fastai/fastpages): This was the first theme I tried and actually used for a while.
It was easy to setup and allows easy publishing of Jupyter notebooks.
The downside is that it is a boilerplate that is hard to customize.
 I cannot find a good way to categorize the articles, for instance, and the search function was not there.   

2. [Beautiful Jekyll](https://beautifuljekyll.com/): Beautiful Jekyll had all the features I needed
except the search function. There should derivative themes that should have the search function, but
I found a better solution so I did not go for this one. 

3. [jdh8](https://jdh8.github.io/): The theme is the WordPress twenty-sixteen theme ported over to Jekyll.
I liked WordPress twenty-sixteen template and still using it for my other blog site.
 The downside is still the search funciton.

In the end, I settled on [zzsza](https://zzsza.github.io/) because it has all the features I needed.
Internally, almost all of these themes are built upon [Hydejack](https://hydejack.com/) which is
another Jekyll theme and so is the reason for the title of this article: Jekyll and Hyde.

## How to setup?

I followed the guideline of [Beautiful Jekyll](https://github.com/daattali/beautiful-jekyll#readme)
to setup the site.

1. Clone the theme
2. Change the repo name to [user id].github.io in your github.
3. Modify and customize to your needs
4. Commit and push.

The blog site is available within a few seconds.