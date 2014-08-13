---
layout: post
title: "CoreOS on Hetzner"
date: 2014-08-13 21:01:14 +0100
comments: true
categories: [coreos, devops]
redirect_from: /s/12.htm
---
I'm going baremetal \o/

<!-- more -->

I followed this [piece of instructions](https://www.penflip.com/jun/iilab-systems/blob/master/CoreOS-on-Hetzner-Bare-Metal.txt).

And there is also the [wiki](http://wiki.hetzner.de/index.php/Installimage/en) that can help :)

```bash
wget https://raw.githubusercontent.com/coreos/init/master/bin/coreos-install
chmod +x coreos-install
cat > config<<EOF
#cloud-config
ssh_authorized_keys:
 - mykey
EOF
./coreos-install -d /dev/sda -C stable -c config
reboot
ssh core@x.x.x.x
```

That's it \o/
