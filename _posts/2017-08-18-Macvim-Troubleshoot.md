---
layout: post
title: "Macvim Troubleshoot"
author: "Zoey Li"
categories: journal
tags: [documentation,sample]
---


While working on iTerm2, a warning came up, "Ultisnips requires Vim >=7.4" and
another line about YouCompleteMe, so I tried to update vim through "brew upgrade
vim". However, at the end of the upgrade, an error came up that says couldn't
find ruby-2.4.something in the library. So I checked my $PATH. 

Not a macros person, very scared and confused by the
/.rvm/gems/ruby-2.4.1/bin:blah blah blah. Having seen rvm on my $PATH variable,
I realized that I recently installed Ruby with RVM to set up my Github Page with
Jekyll. Checking dot files, I saw a .rvm file which might be the reason for
those rvm/gems/ruby prefixes on my $PATH.

I messed with $PATH on my .zshrc file. I don't know how it worked. But when I
remove the rvm/gems/ruby prefixes by sourcing my .zshrc, and then brew upgrade
vim, it worked fine. 

However, another problem pops up, that is "No module named
'encodings...Aborted." My most feared warning. After some web searching, I
realize that I only needed up upgrade my macvim, because I just upgraded vim...
and Viola!


