---
title: "Blog Init"
date: 2022-01-16
author: "Zachary Ranes"
tags: ["Git","Hugo",]
summary: "Starting a blog, writing down my thoughts"
hideSummary: false
draft: false
---

I will be using a simple crutch of the Why, How, What framing, based on the Simon Sinek book "Start with Why", to organize this blog post.

## Why

"Practice" is the first word that comes to mind when asking myself why I wanted to start this blog. The basic writing skills I learned in high school and college will atrophy if not used consistently, so some type of semiformal writing will allow me to keep some level of proficiency. Furthermore, with writing down my thoughts about projects and media, I will be having to summarize what I took away from the experiences, which in turn will allow me to learn more from each experience.

## How

I don't have much interest or expanse in any kind of web development. I also did not have much of a want to learn HTML, CSS, or JavaScript, so I investigated alternative tools to help set up this blog. After some research (and flipping a coin between the last two options that both seem to have all the features I needed), I decided on using HUGO. HUGO is a tool that lets you write blog posts in Markdown and then combine those with one of a large selection of themes to generate the code for a static website.

With the tool to generate the website selected, I still needed to host it somewhere. The idea of self-hosting crossed my mind, as I have an extra home lab server that could run a webserver, but the risk of exposing my home network to the internet, even in a small way, did not seem worth it. So, I went with a more familiar option, which was GitHub Pages. GitHub pages is nice because you can simply upload a static website into a repository and GitHub will server it after configuring a few options in that repositories' settings.

## What

To start I used the HUGO tool to make the blog's working directory, then I setup a git repository in that directory. I set up the theme I chose as a submodule to that main git repository. If you simply clone a repository into a subdirectory of another repository, it will cause errors, so using a submodule is necessary. As you can see from the footer of this post and other pages on the blog, I am using the PaperMod theme. From this point, there are a few ways I could have tried (and did try) to proceed.

When the HUGO tools build the static site, it places it in a subdirectory called 'public'. My first attempt at publishing the site was to make the public folder into a git submodule repository and having it point to another repository on GitHub that is setup to server the site. This way had the advantage of allowing the repository with the full HUGO project to remain private while the finished site was public. However, it also had the downsides of being more complex, due to the second git submodule, and then having two repositories to work with. Overall, this method works, but felt clunky to me, so I went with the way I am working on this post.

The setup for the project is the same as above, but without setting up a git submodule for the public folder. The difference is added a configuration file to the repository that triggers a GitHub workflow. This configuration is provided on the HUGO website, and it allows for the HUGO build to happen on the GitHub server. The GitHub workflow also drops the built blog from the HUGO build into a separate branch of the same repository and, with a change to the settings of the repository, that branch becomes the host to the GitHub Pages site.
