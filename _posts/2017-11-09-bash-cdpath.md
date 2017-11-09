---
layout: post
comments: true
categories: bash
published: true
title: Bash - CDPATH
author: Nils Bolsen
image: nilsbash.png
---
## CDPATH - The search path for the cd command

`cd` TAB+TAB anywhere and get your home folders expanded. Add

```
export CDPATH=.:~
```

to your `~/.bash_profile` or `~/.bashrc` file.

Now if want to change to your ~/Desktop or ~/Downloads folder and you are currently somewhere deep in a projects hierarchie. You do not need to `cd`, to get to your home folder and than `cd Desktop`, you can simply just `cd Desktop`. With TAB-completion you can `cd DesTAB+TAB` and you are there.

You can add as many folders as you want, like your projects folder or media library, just do not forget to leave the dot `.` in; it is the current directory.

![]({{site.baseurl}}/images/nilsbash.png)![nilsbash.png]({{site.baseurl}}/images/nilsbash.png)
