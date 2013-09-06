---
layout: post
title: "My knife was slow, so I sharped it!"
date: 2013-08-01 17:39
comments: true
categories: [on the fly, zsh, chef, knife, rbenv, speed, DevOps]
---

Today, I finally decided to take care of my knife.. `knife help` was taking 30seconds..

<!-- more -->

I use zsh, with the [beautiful agnoster style](https://gist.github.com/agnoster/3712874)! Here is my [zsh file](https://github.com/pierreozoux/dotfiles/blob/master/zshrc).

## This is how I improved the speed of knife
After reading [that thread](http://lists.opscode.com/sympa/arc/chef/2011-05/msg00020.html), I decided to give it a try :
```bash 1. Clean your knife plugin
gem list | grep knife-
gem uninstall knife-unused_plugin
```

```bash 2. Clean your gem env
#At your own risk, I add to reinstall some gem, but it was a lot faster afterward!
gem clean
```
\o/, it's a lot better (3s), but still not satisfied... If you have some hints?
On top of that, my terminal was taking some seconds to load.. Annoyed...

## Make faster the terminal loading
rbenv was taking a bit of time, I tried [this](http://cantina.co/2013/01/25/speeding-up-your-console-when-using-rbenv/)
```bash 3. change the rbenv way of loading
#in zsh config file
eval "$(rbenv init - --no-rehash)"
```

I still had this anoying message "you have new mails", actually, I noticed, that I had an used crontab throwing errors there. And a mail per day since some month...
```bash 4. clean mails
cat /dev/null > /var/mail/pierreozoux
#remove the unused crontab
crontab -e
```

Great, my terminal is loading really fast again, I will be able to relax now :)

As always, feel free to comment/insult/troll!
