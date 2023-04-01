### Configuring Firewall ###
**1. Add Roles**
**1.1 Allowing SSH**
**1.1.1 Allowing SSH by Service Name**
```
sudo ufw allow OpenSSH
```
**1.1.2 Allowing the OpenSSH UFW Application Profile**
```
sudo ufw allow ssh
```

**1.2 Allowing NGINX**
```
sudo ufw allow 'Nginx Full'
```

**1.3 Set default role**
```
sudo ufw default deny incoming
sudo ufw default allow outgoing
```
**1.4 Allow IP range to connect port 3306**
sudo ufw allow from 192.168.1.0/24 to any port 3306

**1.5 Enabling UFW**
```
sudo ufw enable
```
