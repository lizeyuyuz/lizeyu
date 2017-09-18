--- 
layout: post 
title: "First time personal website setup" 
author: "Zoey Li"
categories: journal 
tags: [personal-website] 
---

### Setting up Gihub Pages with RStudio Before going for Jekyll, I was looking
at ways to set up a <span style="color:blue">personal website using RMarkdown
</span>. I found this great example
[here](http://nickstrayer.me/RMarkdown_Sites_tutorial). The process is very
straightforward. You write your posts in RMarkdown, and then run a very simple
R script to convert Rmd files to html files. Then I found that I can host it for
free using [Github Pages](https://pages.github.com).  After reading further
about Github Pages, I learned about [Jekyll](https://jekyllrb.com). I wanted a
minimalist website; something that is simple but not bland, so a themed website
would be great.

### Setting up Github Page with Jekyll.

I installed Jekyll. And followed the [quick-start
guide](https://jekyllrb.com/docs/quickstart/) to create a website with a default
theme called "minima". I also took sometime to read about setting up Github
pages locally with Jekyll. The test sites I created worked fine locally,
however, I encountered some difficulty of displaying the website through Github
Pages.

Side notes about setting up a Github Page: If you create a website through a
repository named `USERNAME.github.io`, your website will be hosted at
[http://USERNAME.github.io](http://USERNAME.github.io). And if you want to set
up any other project pages, they have to be made through this repository but
different branches, specifically `gh-pages` branches. 

Next, I followed a [guide](http://jmcglone.com/guides/github-pages) by Jonathan
McGlone that creates a [demo website](http://hankquinlan.github.io) using Jekyll
and hosting it on Github Pages. The example website's layout is not what I was
looking for, so I went on searching and found the [Larange Jekyll
template](https://github.com/LeNPaul/Lagrange) by Paul Le. Basically, you fork
the repository to your own Github account, changes its name and content or
format however you like, and then you will have a minimalistic themed website of
your own.

- To add/change menu pages, go to `menu` folder and add/change the `.md` files. 
- To add/change posts, go to `_post` folder and add/change `.md` files. Posts
  titles usually have to follow the convention `YYYY-MM-DD-title-of-my-post.md`.
- To change general settings like title, taglines etc, go to `_config.yml` or
  `_data/setting.yml`.
- To add pdfs, `[get the PDF]({{ site.url }}/assets/mydoc.pdf)`.
- To add external links, `[site](url)`
- To add internal links, see [here](https://stackoverflow.com/questions/4629675/jekyll-markdown-internal-links).
- To add color to text, `<span style="color:blue">personal website using RMarkdown
</span>`.

Here is a [Markdown
cheatsheet](https://github.com/adam-p/markdown-here/wiki/Markdown-Cheatsheet).
