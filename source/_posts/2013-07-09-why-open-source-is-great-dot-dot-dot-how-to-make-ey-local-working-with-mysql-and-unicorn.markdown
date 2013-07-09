---
layout: post
title: "Why open source is great... How to make ey-local working with mysql and unicorn"
date: 2013-07-09 15:25
comments: true
categories: [EngineYard, workflow, devops]
published: false
---

When Engine Yard released `ey-local`, I was amazed as it was promising to facilitate my work. But it was a bit (s/bit/lot/) more difficult than `ey-local up`

I'll try to explain quickly how I went thou the obstacles.
<!-- more -->

## Vagrant

I already explained [How to isolate vagrant env](/blog/2013/07/09/how-to-isolate-vagrant-env/), and it was indeed because `ey-local` is using the old vagrant.

## The right workflow

The code of `ey-local` is open source but not in a git repo, so I had to find my way, to make a sustainable workflow.

### Patch the recipes

On the way, I found it would be great to modify as little as possible the current workflow, so I decided to use the `patch` scheme that was already setup in the gem for the recipes.

The 1st issue was that, it was not working out of the box, so I wrote a [first patch](https://github.com/pierreozoux/patches_ey-local/blob/master/patches/required.patch) that make the gem behaving correctly regarding the basics.

### Give back to the community

Looking at the EngineYard support, I saw a great demand for certain features, that I wanted also. So I thought it would be great to give back to the community.

It is how I decided to go thou the creation of this [github repo](https://github.com/pierreozoux/patches_ey-local). So this is a place for us to share our patches for `ey-local`!

Hopefully, EngineYard will reuse this material for the next releases.

## Hacky? Hacky!

Yes it is unfortunately really hacky, and the next step for `ey-local`, would be to modify it so well, that we have a replacement for `ey` command.

It should behave exactly the same, and maybe add a configuration file for the configuration we normally do online!

## That's Why open source is great...

But it would be greater with a git repo :)

As always, feel free to comment/insult/troll!
