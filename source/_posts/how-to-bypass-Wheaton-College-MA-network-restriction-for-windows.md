---
title: how to bypass Wheaton College(MA) network restriction for windows
date: 2016-06-12 11:47:12
category: English Blog
tags:
  - computer
  - Microsoft Edge
---

* if you just want to get onto the internet: jump to [What Should I do](#do)

## Why Do I Write This Blog

If you think I am just one of those naughty kids who likes to breaks the rule,
then you are wrong.

In fact, I love standards:
standards are great because they makes the lives of people easier.
Some standards templatize complicated work,
and make both the creation and usage of the software much easier.
Some other standards puts restrictions on people's behavior 
to achieve the common good.

I love both of the two kinds of standard above.

What I hate is some old and outdated standards,
that does not do any good, and only causes troubles.

For example, the policy to force any Windows user to manually register their mac address (physical address).
This is some outrageous discrimination against Windows users.

I notice that this policy has been setup because windows laptop are more likely to get virus,
and then they need the windows user to install an antivirus software (ESTS)

I think that this wrong for the following reason:

  - windows, especially windows 10 adds tons of security feature in Edge and windows itself:
    - windows defender gets regular update every week
    - edge has smart screen filter that will warn you if you are downloading an `exe` that is not being downloaded very often
    - windows will warn you if you are trying to run a `cmd` or `bat` file you downloaded, and some `exe` that is not being downloaded very often
    - powershell script is disabled by default.
    - if you think that people do not use edge, then force people to download file with edge; I am okay with that.
  - mac has tons of security loop hole too:
    - apple script can easily simulate a prompt to ask people for sudo password. (windows don't have that)
    - remember [xcode ghost](https://en.wikipedia.org/wiki/XcodeGhost)? (there is no visual studio ghost so far)
  - most people just go to tech support to register their mac address, not installing ESTS.
  - for people installed ESTS, they uninstall them once they get on internet.
  - ESTS's REGISTER KEY IS OUT OF DATE, and it breaks my surface book 5 times. (STUPID ESTS!)

Therefore I think that this policy has no effect at all and it is not fair for windows user. 

If there is no one gonna do anything about it, I will.


## some stuff about why the method below works

The register website uses a javascript to get your user agent (browser). 

This is possible because the browser tells the webpage what it is (in the request header there is a string called `user-agent`)

![](/images/bypass_wheaton/user-agent.PNG)

Here is the user agent for Microsoft Edge. Notice the `(Windows NT 10; Win64; x64)`, that says your machine is a 64 bit windows 10 box

Therefore if we can change that line, we can pretend to be any browser we want.


## <a name=do> What Should I do? </a>

* click `F12` in Microsoft Edge to get dev tools

![](/images/bypass_wheaton/dev-tool.PNG)

What you see should be some what like this.

* click `Emulation` Tab

![](/images/bypass_wheaton/Emulation.PNG)

* go to Mode and change `Browser profile` to `Windows 10 Mobile`, this will make your browser looks like windows phone.

![](/images/bypass_wheaton/change_mode.PNG)

* Then go to network registration and click `STUDENTS (Handheld and Phone devices - wireless)`

![](/images/bypass_wheaton/registration.PNG)

* go through normal registration then you should be all set.

* You are on Wheaton Network! Yepy!

## one last thing

Microsoft Edge provides much more rich Emulation than a "normal browser" like chrome and firefox (not to mention, safari).

There are tons of `User agent string` built into Microsoft Edge:

![](/images/bypass_wheaton/Emulation-options.PNG)

You can even emulate iPad!

If you are still not satisfied, you can even choose `custom` and input any `user-agent` string:

![](/images/bypass_wheaton/costum_user_agent.PNG)

All the strings can be found [here](http://www.useragentstring.com/pages/useragentstring.php)

Microsoft Edge Rocks!
