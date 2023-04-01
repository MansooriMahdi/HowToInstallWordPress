### Add subdomain with file listing ###
**1.Creating directory**
```
mkdir /var/www/html/dl.mahdimansoori.ir
```
**2.Add NAME record to BIND service**
```
dl      IN      CNAME   mahdimansoori.ir.
```
**3.Configuring NGINX**
```
server { 
    root /var/www/html/dl.mahdimansoori; 
    server_name dl.mahdimansoori.ir; 

    location / {
	autoindex on;
    }
```
**4.Create certificate with CERTBOT**
```
sudo certbot --nginx -d dl.mahdimansoori.ir
```



