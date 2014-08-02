---
layout: post
title: "Web Sign In and h-card"
date: 2014-08-01 22:57:06 +0100
comments: true
categories: [IndieWeb]
redirect_from: /s/8.htm
---

Now that I own my [domain name](http://localhost:4000/blog/2014/07/31/domain-name-and-github/),
let's setup [Web Sign In](http://indiewebcamp.com/How_to_set_up_web_sign-in_on_your_own_domain) with Octopress.
We'll also add an h-card, so that I own my digital identity.

<!-- more -->

## 1 - add the asides

This one is easy, head to your `source/_includes/asides`, and add the following file:

{% gist 253abe2208270a08918e about_me.html %}

Just add `asides/about_me.html` to your `_config.yml` in `default_asides`, and that's it!

Profit :) You can now sign in the [IndieWebCamp wiki](http://indiewebcamp.com/Special:UserLogin) \o/

## 2 - Use gravatar for your image (optional)

If you want a picture of you also, I took the decision to use gravatar. To make this working,
just `cd plugins; wget https://raw.githubusercontent.com/joet3ch/gravatar-octopress/master/gravatar.rb`

Thanks [joet3ch](https://github.com/joet3ch/gravatar-octopress) for his plugin :)
(Unfortunatelly, I'll not be able to webmention him because, he is not part of IndieWeb.. We'll learn about webmention soon!)

## Final thoughts

I now control my identity online!
