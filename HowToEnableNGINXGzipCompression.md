![How to Enable NGINX Gzip Compression](images/gzip-compression-nginx.jpg)
**GZIP** compression allows NGINX server to compress data before sending it to client browser. This reduces data bandwidth, improves website speed and saves server costs. Here are the steps to enable NGINX GZip compression.

**1. How to Enable NGINX Gzip Compression**

**1.1 Open NGINX Configuration file**
Open terminal and run the following command to open NGINX server configuration file.
```
sudo vi /etc/nginx/nginx.conf
```
> \
> :bulb: **Tip:** If you have configured separate virtual hosts for your website (e.g www.mahdimansoori.ir), such as /etc/nginx/sites-enabled/website.conf then open its configuration with the following command:
> ```
>sudo vi /etc/nginx/sites-enabled/website.conf
>```
> <br>
