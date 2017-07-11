---
title: Poor Response Times
authors: 
- name: Tim Murphy
  email: tim@26tp.com
---
Yesterday I was alerted by [Uptime Robot](http://uptimerobot.com/) that croquetscores.com had gone down for the first time since moving to [Azure](http://www.azure.com) December 2014. A simple reboot of the server resolved the problem. The logs showed that the server's CPU usage had been sitting at 98% for the past two hours. Early January I saw CPU usage spikes but they went away and I hoped the same would be true this time. Not to be. Chris Clarke alerted me last night the croquetscores.com was slow, thank you Chris. So another quick reboot to resolve the issue but I knew I would have to look into it further this morning. Sure enough this morning the site was sluggish and CPU usage was sitting in high 90% band. It is usually at 5-8% usage.

## Step 1 - Increased server capacity (Implemented)

croquetscores.com now runs on two servers. These two servers sit behind a load balancer that sends your page requests to the server with least load. This setup has a number of advantages. The three main advantages are:

- Improved response times, especially at peak times.
- I can take a server off-line for maintenance and croquetscores.com will continue to serve pages from the other server.
- While writing this blog post I'm monitoring CPU usage. Already there has been a spike. Now there are two servers the load balancer automatically sent all traffic to the good server and the site continued responding at an acceptable pace. In the background I reset the bad server without interruption to site visitors.

## Step 2 - Find what is causing CPU spike

At best Step 1 is only a stop gap measure. I have to find what is causing the CPU usage spikes. This is probably going to be very tedious and time consuming. My current theory is there is a rarely used piece of code that is using a number of resources and failing to release them when finished. If this is the case then it must be only a small number of tournaments that triggers it. I'll test this theory by running an automated process to crawl the website and monitor when the CPU usage spikes.

Wish me luck.

UPDATE: See [Poor Response Times Fixed](poor-response-times-fixed) to find out what the problem was and how it fixed.
