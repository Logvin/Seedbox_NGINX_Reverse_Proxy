# Seedbox_NGINX_Reverse_Proxy

## What is this stuff?
I use NGINX on my dedicated server to serve as a front-end for my various web-accessable apps. To stay secure, I secure my site with SSL encryption from LetsEncrypt, then use a reverse proxy to front end the various apps.

## What is with the individual conf.d items?
Typically, all of the apps are located under the same domain, so rather than having seperate server blocks, my conf.d files are actually location blocks. I do this so my nginx.conf file is much cleaner, and it helps me seperate the various web apps into individual files.

## What does the end result look like?
All of my apps are accessable by going to https://my.domain/appname. Alternatively, I use Organizr as an additional layer, so I can go directly to https://my.domain and have access to my apps from one portal.

## Why is plex.conf not in the conf.d folder?
I utilize a second IP address to route my plex server access through cloudflare. Cloudflare is a peering service that offers free https peering, which is insanely helpful for getting better speeds due to their massive peering network. I could barely stream a 480p video in plex before I started using cloudflare, have no problem with 4K streams today.
