---
layout: post
title: "How to configure ngnix settings"
subtitle: "Optimal ways to configure nginx"
categories: coding
tags: web
comments: true
---

## To set session timeout value

Modify the config settings in /etc/nginx/nginx.conf

```buildoutcfg
worker_processes 1;
worker_connections 1024;
```

The worker_processes is best to set as the number of processors (cores) of your server
and the recommended worker_connections is 1024.
Here is the formula to calculate the number of active client connections
an ngnix server can handle. 

```
worker_processes x worker_connections = max number of active client connections
```
 
## Reference
* [How to optimize nginx configuration](https://www.digitalocean.com/community/tutorials/how-to-optimize-nginx-configuration)

