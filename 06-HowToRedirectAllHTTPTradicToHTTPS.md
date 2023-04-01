### How to redirect all http traffic to http ###
**1. Add this config to virtual host config for redirects any traffic to the correct HTTPS server block**
```
return 301 https://$host$request_uri
```
