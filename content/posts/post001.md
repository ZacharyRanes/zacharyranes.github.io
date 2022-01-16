---
title: "Blog Init"
date: 2022-01-15
author: "Zachary Ranes"
tags: ["Git","Hugo",]
summary: "Starting a blog, writing down my thoughts"
hideSummary: false
draft: true
---

I will be using a simple crutch of the Why, How, What framing, ripped right from the Simon Sinek book, to organize this blog post.

## Why

"Practice" is the first word that comes to mind when asking myself why I wanted to start this blog. The basic writing skills I learned in high school and college will atrophy if not used, so some type of semi formal writing will hopefully allow me to keep some level of proficiency at writing.  Furthermore by writing down my thoughts about projects and media, having to summarize what I took away from the experiences, I hope to learn more from each experiences.

## How

I don't have much interest or expanse in any kind of web development. Also I did not have much of a want to learn HTML, CSS, and Java Script so I looked into other tools to help setup a blog. After some research and in the end just flapping a coin between the last two options that both seems to have all the features I needed, I decided on using HUGO.  HUGO is a tool that lets you write blog post in Markdown and combine those with one of a large selection of themes to generate the code for a static website. With the tool to generate the website selected, I still needed to host it somewhere. The idea of self hosting it crossed my mind, I have an extra home lab server that could run a webserver, but  the risk of exposing my home network to the internet even in a small way did not seem work it. So doing even less research I decided to go with an option I had already new about, that being GitHub Pages. GitHub pages is nice because you can simply upload a static website into a repository  and GitHub will server it after configuring a few options in that repositories' settings.

## What

I used the HUGO tool to make the blogs working directory then I setup a git repository in that directory. I setup up the theme I chose as a submodule to that main git repository, If you simply clone a repository into a subdirectory of another repository it will cause errors so using a submodule is necessary.  As you can see from the footer of this post and other pages on the blog I am using the PaperMod theme. From this point there are a few way I could have, and did try, to proceed.

When the HUGO tools build the static site is places it in a subdirectory called public. The first way I tried to publishing the site was to make the public folder into a git submodule repository and having it point to another repository on GitHub that is setup to server the site. This way had the advantage of allowing the repository that had the full HUGO project to be private and just the finished site being public. However it had the downsides of being a more complex due to the git submodule and also then having two repository to work with. After trial and error of a few other ways, I ended up at the way I worked on this very post.

Using a GitHub workflow provided on the HUGO website, I do not even need to build the site locally before pushing the whole blog project to one repository. The workflow preforms the HUGO build sever side and puts the contents of that build into another branch witch is set to server the site. I find this method very streamlined and really lets me just worry about the contents of the blog.
