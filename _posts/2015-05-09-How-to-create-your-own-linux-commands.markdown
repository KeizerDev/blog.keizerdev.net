---
layout: post
title:  "How to create your own linux commands"
description: "Just a simple guide if you was wondering how you can."
date:   2015-05-09 15:59:48
categories: bash
---

I've you are working on Ubuntu you can simple edit your .bashrc and add your functions at the bottom of that file.
So in your terminal you just do:
{% highlight bash %}
$ nano .bashrc
{% endhighlight %}
Add some function that you want to the bottom and save it. 
To make it work you have to recompile your .bashrc with the following command:
{% highlight bash %}
$ source .bashrc
{% endhighlight %}

**Some useful functions:**
{% highlight bash %}
extract () {
  if [ -f $1 ] ; then
      case $1 in
          *.tar.bz2)   tar xvjf $1    ;;
          *.tar.gz)    tar xvzf $1    ;;
          *.bz2)       bunzip2 $1     ;;
          *.rar)       rar x $1       ;;
          *.gz)        gunzip $1      ;;
          *.tar)       tar xvf $1     ;;
          *.tbz2)      tar xvjf $1    ;;
          *.tgz)       tar xvzf $1    ;;
          *.zip)       unzip $1       ;;
          *.Z)         uncompress $1  ;;
          *.7z)        7z x $1        ;;
          *)           echo "don't know how to extract '$1'..." ;;
      esac
  else
      echo "'$1' is not a valid file!"
  fi
}
{% endhighlight %}
This function can be used using:
{% highlight bash %}
$ extract filename.rar
{% endhighlight %}
