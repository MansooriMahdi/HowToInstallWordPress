### How to only allow ssh key login and disable passwords ###
**1. Editing sshd_config**
```
sudo nano /etc/ssh/sshd_config
```
Set up following directives to only allow ssh keys based login and disable passwords:
```
ChallengeResponseAuthentication no
PasswordAuthentication no
PermitRootLogin no
PermitRootLogin prohibit-password
```

**2. Generate and add SSH key to server**


**3. Restart or reload sshd**
On your server run
```
sudo systemct reload sshd.service
```