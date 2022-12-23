# Install Fail2Ban
(https://www.adminbyaccident.com/freebsd/how-to-freebsd/how-to-install-fail2ban-on-freebsd/)<br>
pkg search fail2ban<br>
pkg install py39-fail2ban-1.0.1_2<br>
vi /usr/local/etc/fail2ban/jail.d/ssh-ipfw.local
```
[ssh-ipfw]
enabled = true
filter = sshd
action = ipfw[name=SSH, port=ssh, protocol=tcp]
logpath = /var/log/auth.log
findtime = 600
maxretry = 3
bantime = 3600
```
sysrc fail2ban_enable="YES"
service fail2ban onestart

# Install SSHPass
pkg install wget<br>
wget https://pkg.freebsd.org/FreeBSD:13:amd64/latest/All/sshpass-1.09.pkg<br>
pkg add sshpass-1.09.pkg<br>
<br>
Use: sshpass -p "myPassword" ssh -o StrictHostKeyChecking=accept-new username@192.168.1.12