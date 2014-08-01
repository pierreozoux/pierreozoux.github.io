---
layout: post
title: "Web Sign In"
date: 2014-08-01 22:57:06 +0100
comments: true
categories: [IndieWeb]
---

Now that I own my [domain name](http://localhost:4000/blog/2014/07/31/domain-name-and-github/),
let's setup [Web Sign In](http://indiewebcamp.com/How_to_set_up_web_sign-in_on_your_own_domain) with Octopress.

<!-- more -->

This one is easy, head to your `source/_includes/asides`, and add the following file:

{% gist 253abe2208270a08918e web_sign_in.html %}

Just add `asides/web_sign_in.html` to your `_config.yml` in `default_asides`, and that's it!

Profit :) You can now sign in the [IndieWebCamp wiki](http://indiewebcamp.com/Special:UserLogin) \o/
