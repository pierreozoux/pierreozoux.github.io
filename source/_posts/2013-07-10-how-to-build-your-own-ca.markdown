---
layout: post
title: "How to build your own CA?"
date: 2013-07-10 14:26
comments: true
categories: [sysadmin, security]
---

Every time you selfsign a certificate, one of them is dying!

{% img https://placekitten.com/890/280 %}
<!-- more -->


You like them, right? So create a rootCA, install it and sign your cert with!

# Create the rootCA

``` bash Create the rootCA
# create private root key
openssl genrsa -out rootCA.key 4096
# sign it
openssl req -x509 -new -nodes -key rootCA.key -days 1024 -out rootCA.pem
```

# Install the rootCA on the clients

Make it available to your clients, download and install it.

```bash Make it available
cp rootCA.pem /var/www
# -- on your client
wget rootCA.pem # and install
```

# Sign your certificates

And now, for every device that need to be signed (like your intranet website!)

``` bash Create a certificate
#  -- on your device
# create the device private key
openssl genrsa -out device.key 4096
# create the certificate signing request
# common-name is the most important field, this is what your browser will "certify"
# if you website is www.example.com, then put "www.example.com"
openssl req -new -key device.key -out device.csr
# -- on your server with your rootCA
openssl x509 -req -in device.csr -CA rootCA.pem -CAkey rootCA.key -CAcreateserial -out device.crt -days 500
```

That's it! Everytime you visit one of your website, you'll never see again this warning!
{% img center /images/cat_crying.jpg 'cat_crying' %}
Remember, every time you see this, a cat is suffering somewhere in the world, so contact the admin and explain that you love animals!

The quick and dirty tuto is over, if you want to make it better, read the following sources.

[source 1](http://www.davidpashley.com/articles/becoming-a-x-509-certificate-authority/)
[source 2](http://datacenteroverlords.com/2012/03/01/creating-your-own-ssl-certificate-authority/)
