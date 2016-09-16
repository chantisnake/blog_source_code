---
title: git installation and basic configuration
date: 2016-06-05 15:07:24
tags:
  - git
  - powershell
categories: computer
---

* Please note that git is far more powerful than this blog can cover.

If you want to learn more about git, 
I find this video helpful to establish some good git habits:
[Advanced Git Topic](https://channel9.msdn.com/events/MVP-RD-Americas/GitHub--Microsoft-Partnership/GH3-AdvancedGit-commits-stash-stagingarea).
This video is created by one of the employer of GitHub and bunch of Microsoft MVP's.

## installing git

### ubuntu (debian)

```bash
sudo apt-get install git
```

### mac

I think mac has git built in...
if not, I am pretty sure you can use [homebrew](http://brew.sh/):

```bash
brew install git
```

### windows

[chocolety](https://chocolatey.org/) is the way I will recommend it.
Run powershell in admin, then do this:

```bash
choco install git
```

Posh-git is extremely helpful on windows, install it using:

```bash
choco install poshgit 
```

## setting up ssh key

If you are using [GitHub Desktop](https://desktop.github.com/) on windows or mac, you can skip this.

I personally prefer to use the command line, because this is universal, and provides great scripting scripting ability right inside your shell.

### mac and linux

ssh-key setup on mac or linux is pretty easy, follow the instruction here: [generate ssh key](https://help.github.com/articles/generating-an-ssh-key/)

All you need to do is:

```bash
# generate ssh key
$ ssh-keygen -t rsa -b 4096 -C "your_email@example.com"

# turn on ssh-agent
$ eval "$(ssh-agent -s)"

# add ssh-key
$ ssh-add ~/.ssh/id_rsa

# linux copy public key to clip board
$ sudo apt-get install xclip
$ xclip -sel clip < ~/.ssh/id_rsa.pub

# mac copy public key to clip board
$ pbcopy < ~/.ssh/id_rsa.pub
```

Don't forget to change `"your_email@example.com"` on the second line to your registered email of GitHub 

now all you need to do is to add your ssh-key to paste your ssh to your GitHub, see this tutorial: [Adding a new SSH key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)

### windows
adding a ssh-key to windows is a little trickier, luckily people realize that...

Here is a basic tutorial on git for windows and git integration on visual studio if you are interested: [Git Basics](https://channel9.msdn.com/Series/Using-Git-with-Visual-Studio-2013)

There are two ways:

#### use a script.

If you uses chocolatey to installed git, you can automate your ssh-keygen using this powershell script:

```powershell
# get current location
$location = Get-Location

# go to git location
Set-Location 'C:\Program Files\Git\usr\bin'

# genrate and add ssh key
Invoke-Expression './ssh-keygen.exe -t rsa -b 4096 -C "your_email@example.com"'
Invoke-Expression './ssh-agent -s'
Invoke-Expression "./ssh-add.exe $HOME/.ssh/id_rsa"

# copy ssh key to clip board
cat "$HOME\.ssh\id_rsa.pub" |clip

# go back to the original location
Set-Location $location

# log
Write-Host 'your ssh agent is setted up and your ssh key is copied to clip board'
Read-Host 'press enter to continue'
```

Remember to change `"your_email@example.com"` on the first line of `genrate and add ssh key` to your registered email on GitHub.

Now all you need to do is to add your ssh-key to paste your ssh to your GitHub, see this tutorial: [Adding a new SSH key to your GitHub account](https://help.github.com/articles/adding-a-new-ssh-key-to-your-github-account/)


This script is part of my windows setup script: [windows essential](https://github.com/chantisnake/WindowsEssencial) 

#### using `Git-Credential-Manager-for-Windows`

I have never used this before.

Install it using:

```bash
choco install git-credential-manager-for-windows
```

here is the document and the repo [Git Credential Manager for Windows](https://github.com/Microsoft/Git-Credential-Manager-for-Windows)

This seems like awesome... Here is a paragraph of the readme: 

> ### How to use
>
> You don't. It magically works when credentials are needed. For example, when pushing to Visual Studio Team Services, it automatically opens a window and initializes an oauth2 flow to get your token.


