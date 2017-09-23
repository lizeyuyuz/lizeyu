---
layout: post
title: "Neovim Setup"
author: "Zoey Li"
categories: journal
tags: [Neovim, nvim]
---

## Setting up Neovim

Copy `.vim/vimrc` file to `.config/nvim/init.vim`. Do not symlink them, I think it's easier to keep track if you keep them separate. Settings for nvim are somewhat different. 

- For Neovim plugins, install `vim-plug` and create a folder called `plugged` in `.config/nvim` to store all the plugins.

Next install: 

- Neovim Solarized Theme: put this line `Plug "iCyMind/NeoSolarized"` on `init.vim`, and then put `set termguicolors`, `colorscheme NeoSolarized`, and `set background=dark` on `init.vim`.
- YouCompleteMe: put this line `Plug "Valloric/YouCompleteMe"` on init.vim, and then `cd .config/nvim/plugged/YouCompleteMe` and run `./install.sh`. 

- auto-pairs: copy the `.vim/plugin/auto-pairs.vim` to the `nvim` folder, and change the fast wrap key minding from <M-e>, which does not work to <C-l>.

The rest of the packages are installed likewise in `vim-plug` as in `vundle`.

I also installed `Ultisnip`, `Snipmate`, `vim-snippets`, `vim-airline`, `Nvim-R`, `Syntastic`, `vimtex`. For settings of these packages, see my `vimrc` file [here]("https://github.com/lizeyuyuz/vimconfig").


