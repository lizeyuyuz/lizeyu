--- 
layout: post 
title: "About Git Workflow" 
author: "Zoey Li"
categories: journal 
tags: [Git] 
---

## Pushing an existing local folder to repository on Github on command line. 

[Github official guide here](https://help.github.com/articles/adding-an-existing-project-to-github-using-the-command-line/)

1. Create an empty repository, without README.md and without .gitignore files. 
2. Copy HTTP `https://github.com/lizeyuyuz/hi.git`
3. Get to your local folder on terminal, and start by `git init`
4. Stage all local files by `git add .` or stage selected local files by `git add
   [filenames]`
5. Commit your changes by `git commit -m "whatever neecssary"`
6. Add your newly created remote repository by `git remote add origin https://github.com/lizeyuyuz/hi.git`
7. Check your tracking remotes by `git remote -v`
8. Push your local files to remote by `git push -u origin master`

- If you want to undo the `git init` step, do `rm -rf .git`

