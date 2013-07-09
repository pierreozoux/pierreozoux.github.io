---
layout: post
title: "How to isolate vagrant env"
date: 2013-07-09 15:06
comments: true
categories: [vagrant, devops, zsh]
---

As you may have noticed, vagrant changed version. Of course, I downloaded the last version. The issue is that, there is a `.vagrant.d` in your home that help to configure it, and different version of vagrant use different configurations.

I wanted a totally isolated environment. I'm now using a `Runmefile` in my environment to change the pointer to the `.vagrant.d` folder.

<!-- more -->

Here is how I did it :

``` bash Add a hook in your .zshrc https://github.com/pierreozoux/dotfiles/blob/master/zshrc#L76 my .zshrc
_within-runme-project() {
  local check_dir=$PWD
  if [ $check_dir != "/" ]; then
    [ -f "$check_dir/Runmefile" ] && return
  fi
  false
}

function chpwd() {
  if _within-runme-project; then
    source ./Runmefile
  fi
}
```

And Add a `Runmefile` in your project :
{% gist 5798032 Runmefile %}

Now each time you `cd`to your working directory, it'll change your pointer to `.vagrant.d` folder \o/

As always, feel free to comment/insult/troll!
