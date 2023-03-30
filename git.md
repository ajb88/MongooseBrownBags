## git
* A version control system tracks and manages changes to software code
* There have been many version control systems over the years and many current alternatives
  * RCS, CVS, Subversion
  * Perforce, Bazaar, Mercurial
* Git is the undisputed king
* Created by Linus Torvalds to host the Linux Kernel, designed to be used by a Unix-like command line
* Git is complex and has a steep learning curve, but we can still be productive with a relatively small set of commands
![Haha xkcd](https://imgs.xkcd.com/comics/git.png)

### config 
* Set up your commit data and utilities

```bash
$ git config --global user.name "ajb"
$ git config --global user.email "ajb@aol.com"

# Git opens a text editor everytime we commit
# Be careful! vi is the default! Gross!
$ git config --global core.editor emacs

git config --global init.defaultBranch main

git config --global color.ui "auto"
```
### create a new repository

```bash
$ mkdir project && cd project
$ git init
```

### workflow
* There are three trees in git:
  * Working Directory - the actual files
  * Index - staging areas
  * HEAD - points to the last commit
![workflow](https://rogerdudler.github.io/git-guide/img/trees.png)

* Once we add a file, we can use ```git status``` to see what's going on 

```bash
ajb@pop-os ~/c/c/MongooseBrownBags (main)> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes not staged for commit:
  (use "git add <file>..." to update what will be committed)
  (use "git restore <file>..." to discard changes in working directory)
	modified:   Makefile

Untracked files:
  (use "git add <file>..." to include in what will be committed)
	git.md

no changes added to commit (use "git add" and/or "git commit -a")

```

* We can propose changes (add to index) using ```git add```

``` bash
ajb@pop-os ~/c/c/MongooseBrownBags (main)> git add -A
ajb@pop-os ~/c/c/MongooseBrownBags (main)> git status
On branch main
Your branch is up to date with 'origin/main'.

Changes to be committed:
  (use "git restore --staged <file>..." to unstage)
	modified:   Makefile
	new file:   git.md
```

