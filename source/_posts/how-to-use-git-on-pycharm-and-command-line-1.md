---
title: how to use git on both pycharm and command line (1)
date: 2016-06-05 21:25:20
tags: 
  - pycharm
  - powershell
  - git
categories: computer
---

This section we will introduce couple of commonly used git command and how to use them both in command line and pycharm

* **all the following demo is using gvim, pycharm on windows 10 and powershell 5 with ConEmu**


## git add 

### command line

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

I will create a new file called `test`:

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



