--- 
layout: post 
title: "New Mac Setup" 
author: "Zoey Li"
categories: journal 
tags: [personal-website] 
---

## Install Python3
Install from traditional distributor (YouCompleteMe is not compatible with
Anaconda Python)

## Install Macvim with Python3 support
Soultion found [here](https://www.reddit.com/r/vim/comments/2kul8h/macvim_with_python3/). So when you run `:python3 import sys; print(sys.version)` in vim, it should work.

## Installing YouCompleteMe
Find instruction here [YouCompleteMe](https://github.com/Valloric/YouCompleteMe#mac-os-x).

### Problems I ran into while trying to install YouCompleteMe
when installing cmake, `brew link cmake` gives errors.  
Solution found [here](https://stackoverflow.com/questions/18857408/cannot-install-cmake-for-mac-os-x-10-8)

```shell_session

/usr/bin/ruby -e "$(curl -fsSL https://raw.githubusercontent.com/Homebrew/install/master/install)
brew link cmake
```

### Tab to cycle through autocomplete drop-down menu not working properly
Solution: add this plugin `"Plugin 'ervandew/supertab'` to your vimrc

## Install Jekyll

### Requirements

- GNU/Linux, Unix, or macOS
- Ruby version 2.1 above (install with RVM: see below)

`gem install jekyll`

### Install ruby with RVM

```shell_session

sudo gpg --keyserver hkp://keys.gnupg.net --recv-keys 409B6B1796C275462A1703113804BB82D39DC0E3
curl -sSL https://get.rvm.io | sudo bash -s stable
sudo usermod -a -G rvm `whoami`
rvm install ruby-2.4.10
gem install jekyll
```
