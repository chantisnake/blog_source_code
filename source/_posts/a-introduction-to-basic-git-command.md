---
title: a introduction to basic git command
date: 2016-06-05 15:34:25
tags: English Blog
categories: computer
---

* **Please note that git is far more powerful than this blog can cover.**

If you want to learn more about git, 
I find this video helpful to establish some good git habits:
[Advanced Git Topic](https://channel9.msdn.com/events/MVP-RD-Americas/GitHub--Microsoft-Partnership/GH3-AdvancedGit-commits-stash-stagingarea).
This video is created by one of the employer of GitHub and bunch of Microsoft MVP's.


* **all the following demo is using gvim, pycharm on windows 10 and powershell 5 with ConEmu**


## Important Git Concepts


### commit 
This is the hardest concept I will introduce in this article.

Commit is basically like a **saving point of your program**. 
Every time you created a commit means you have saved you current image of your program inside of a git.

* Noticed what saved inside of the git is actually the **difference between your current commit and your previous commit** .
Therefore when we say **"applying a commit to a program"** means redo all the actions you did from the last commit to a program.

For example, I have a code project looks like this:
![](/images/git_basic/befor_change.PNG)

After I added two line:
![](/images/git_basic/after_change.PNG)

After I commit this change, the two lines, inside git will say that I added two lines on the `New_File`(this is the file name of the file I am changing) in this commit.
So if we say that "apply this commit to local" means add these two lines on the `New_File` on `local`(this is the concept we will encounter later) 

### local and remote

Because one of the power of the git is to backup all your code on a remote server(which is just another computer that is connected to the internet),
therefore git need a `remote` server and your own `local` computer.

The syncing between the server (`remote`) and your current computer (`local`) is manual, not automatic real time syncing,
and also because there are other people using the same server to `colaborate` (which just means to edit the same code project at the same time), therefore there can be difference between local and remote.


## Git Commands

This section we will introduce couple of commonly used git command and how to use them both in command line and pycharm


### git add 

#### command line

this command adds changes in to your git info, and waiting to be committed.

`git add .` and `git add -A` will automatically adds all the file that is changed from the last commit.

Examples:

![](/images/git_basic/git_status.PNG)

we will explain git status later.

You can see that I have two changes, notice those changes is to compare with the last commit **on your local**: 

  * modified the file `New_File` (I added two line at the end)
  * deleted `toy.md`
  * and added a `.toy.md.swp`

So if I do `git add .`:

![](/images/git_basic/git_add_dot.PNG)

All the change is added and ready to be committed (see that on the top `Changes to be committed`)

if I do `git add -A` this will have the exact same effect:

![](/images/git_basic/git_add_minusA.PNG)

* notice there is a indication on the top that looks like `[master +1 ~1 -1 ~]`.
That is `posh-git` on powershell. 
`+1` means there is one addition(`.toy.md.swp`); 
`~1` means there is one modification (`New_File`);
`-1` means there is one deletion (`toy.md`).
This is really handy

If I think that the addition of `.toy.md.swp` is a mistake, I don't want it to be pushed to the remote.
Or I just haven't finish all the things I am working on in `.toy.md.swp`, 
then we can just add `New_File` and `toy.md`

I can just do `git add New_File toy.md`

![](/images/git_basic/git_add_selected.PNG)

* notice `posh-git` left the `+1` orange, which means the addition of `.toy.md.swp` is not added. 
On the other hand, the blue `~1` and `-1` means the modification and deletion is added.

### pycharm

If you create a file on pycharm in a git directory, 
pycharm will automatically prompt you for whether to add this file.

I will create a new file call test:

![](/images/git_basic/pycharm_new_file.PNG)

pycharm will ask me once the file is created:

![](/images/git_basic/pycharm_git_add_promp.PNG)

So if there is some file I did not add in pycharm or I forget to check `yes` when I created this file,
I can always right click on the file and go to `git -> add`

![](/images/git_basic/pycharm_git_add_manual.PNG)

After adding notice that the file name turns green:

![](/images/git_basic/pycharm_git_add_after.PNG)

Green file name indicates new file, and blue file name means changed files.

## git commit 


