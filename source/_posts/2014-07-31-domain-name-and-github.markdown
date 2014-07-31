---
layout: post
title: "Domain name and github"
date: 2014-07-31 14:34:38 +0100
comments: true
categories: [IndieWeb]
---

This is the first article on how to IndieWebifyme with Octopress and GitHub. This is the first part of the level 1, 
get a domain name.

<!-- more -->

## Prerequisites
To start, I'll assume you have a working octopress with github pages.

## 1 - Domain name
So to IndieWebify me, the first step is the domain name. I bought [pierre-o.fr](http://www.pierre-o.fr) for 5€/y.
I use [bookmyname](https://www.bookmyname.com/) as registrar.
I find it is the cheapest, service is simple and working.

## 2 - CNAME in the DNS registrar
Go to your registrar (or DNS provider) and configure the CNAME to point to your github username.
```bash config for DNS
www CNAME pierreozoux.github.io
```

## 3 - CNAME file in the project
Then, just add a CNAME file into your project with this content:
```bash CNAME
www.pierre-o.fr
```

That's it! Commit your change, generate and deploy!

## Final thoughts

I now own my online indentity. The domain name that represent the entry point of my online indentity belongs to me.
Nobody can close this service, ask me 100€ for that, or censor me from now on! Of course we can discuss this
concept with the light that DNS is centralised, but it is a lot better than a namespace behind facebook walls!

If you have any questions/doubts, please, let me know!
