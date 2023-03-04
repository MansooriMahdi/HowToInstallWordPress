![Hide Your NGINX Server Version](images/hidenginversion.jpg)

**Hide Your NGINX Server Version**
Banner grabbing is the act of scanning websites to find server information including services and open ports. This technique is used during vulnerability assessments. Hiding your NGINX server version from scanning tools makes it harder for hackers to know what vulnerabilities can be exploited on your server.

**1. View and Hide NGINX Server Header Information**
You can use the following terminal command to check your current server information.

```
curl --head yourdomain.com or IP
```

> :bulb: **Tip:** You can also view this information with online tools such as https://securityheaders.com and https://observatory.mozilla.org. However, you’ll still need to access the terminal to make necessary changes to your server.

\
**Output:**
```
HTTP/1.1 302 Found
Server: nginx/1.18.0 (Ubuntu)
Date: Sat, 04 Mar 2023 19:35:28 GMT
Content-Type: text/html; charset=UTF-8
Connection: keep-alive
Location: http://localhost/wp-admin/setup-config.php
```

We’ll remove that version number to make it just a little harder for cyber attackers to infect your server.

**Step 1. Edit the NGINX configuration file:**
```
vim /etc/nginx/nginx.conf
```
**Step 2. Under the # HTTP Options and ## lines, add a new line:**
```
server_tokens off;
```
**Step 3. Restart NGINX Server**
Run the following command to check syntax of your updated config file.
```
sudo nginx -t
```
If there are no errors, run the following command to restart NGINX server.

```
sudo service nginx reload
```
**Step 4. Check again your NGINX server information:**
```
curl --head yourdomain.com or IP
```
\
**Output:**
```
HTTP/1.1 302 Found
Server: nginx
Date: Sat, 04 Mar 2023 19:43:30 GMT
Content-Type: text/html; charset=UTF-8
Connection: keep-alive
Location: http://localhost/wp-admin/setup-config.php
```