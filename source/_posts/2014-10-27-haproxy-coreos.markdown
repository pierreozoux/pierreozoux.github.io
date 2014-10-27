---
layout: post
title: "HAproxy on CoreOS"
date: 2014-08-27 10:01:14 +0100
comments: true
categories: [coreos, devops, haproxy]
redirect_from: /s/13.htm
---
What are the best practices of running HAproxy on CoreOS?

<!-- more -->

## Dear fellow hackers,

I'm discovering CoreOS, and I have to say, I enjoy it, it's really thrilling to learn all this new and exciting technology!

I'm trying to follow as much as possible best practices for Docker, 12-Factor App and so on. But for HAproxy, I'm hitting the wall. So here is my problem:

12-Factor app recommendation for logging is to have a process that sends out logs directly to stdout/stderr, and then your process management has to catch it somehow, and you can do whatever.

In the other hand, Docker recommendation is to run just one process per container.

Until now, I was totally fine. Systemd was catching output from my docker container, and everybody was happy. But what about HAproxy?

So, I realised it was impossible to log to stdout except in debug mode. This is the solution I'll use for now, but I feel it's not that elegant...

The other solution I found would be to run a container with rsyslogd listening on docker_gateway:514, and then configure HAproxy to send it's UDP packets to this gateway... But well, it's not that elegant neither..

I'm open for suggestions to make it wonderful!
