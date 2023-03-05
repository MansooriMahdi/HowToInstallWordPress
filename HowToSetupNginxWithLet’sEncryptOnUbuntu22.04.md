**How to Setup Nginx with Let’s Encrypt on Ubuntu 22.04**
This tutorial will cover on how you can setup nginx with lets encrypt on ubuntu 20.04.

> :bulb: **Tip:** Let’s Encrypt is a non-profit certificate authority run by Internet Security Research Group that provides X.509 certificates for Transport Layer Security encryption at no charge.

Steps on How to Setup Nginx with Let’s Encrypt on Ubuntu 22.04:
■ **Step 1: Install Certbot**\
■ **Step 2: Check Nginx Configuration**\
■ **Step 3: Allowing HTTPS Through the Firewall**\
■ **Step 4: Get Free SSL/TLS Certificate**\
■ **[Step 5: Enable Automatic Certificate Renewal](#step-5-enable-automatic-certificate-renewal)**

### Step 1: Install Certbot ###
Firstly, We are going to install certbot. To install run the following command line.

```
sudo apt update
sudo apt install certbot python3-certbot-nginx
```

### [Step 2: Check Nginx Configuration] ###
Run the following command on the command line to check that it is set up correctly.

```
sudo nano /etc/nginx/sites-available/example.com
```

You want to include a domain name with and without www. So enter the following command.


```
server_name example.com www.example.com
```

### Step 3: Allowing HTTPS Through the Firewall ###
So now, by the following command check the firewall status.

```
sudo ufw status
```

Allow Nginx full profile and type the following command to delete unnecessary Nginx HTTP profile allowance.

```
sudo ufw allow 'Nginx Full'
sudo ufw delete allow 'Nginx HTTP'
```

### Step 4: Get Free SSL/TLS Certificate ###
Now, execute the following command on command line to get free ssl/tls certificate.

```
sudo certbot --nginx -d example.com -d www.example.com
```

### [Step 5: Enable Automatic Certificate Renewal] ###
Use the following command on the command line to create automatic renewal:

```
sudo systemctl status snap.certbot.renew.service
```

To test the renewal process, Use the dry command with certbot:

```
sudo certbot renew --dry-run
```
