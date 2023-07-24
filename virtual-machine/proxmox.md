# Upgrade Proxmox
apt update && apt upgrade -y && apt dist-upgrade -y

# Remove Proxmox enterprise
nano /etc/apt/sources.list.d/pve-enterprise.list
-> comment first line -> Save -> exit.

# Remove Proxmox Subscription Notice
Source: https://johnscs.com/remove-proxmox51-subscription-notice/
```
sed -Ezi.bak "s/(Ext.Msg.show\(\{\s+title: gettext\('No valid sub)/void\(\{ \/\/\1/g" /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js && systemctl restart pveproxy.service
```

# Use no subsciption repository
Source: https://pve.proxmox.com/wiki/Package_Repositories#sysadmin_no_subscription_repo \
nano /etc/apt/sources.list
```
deb http://ftp.debian.org/debian bullseye main contrib
deb http://ftp.debian.org/debian bullseye-updates main contrib

# PVE pve-no-subscription repository provided by proxmox.com,
# NOT recommended for production use
deb http://download.proxmox.com/debian/pve bullseye pve-no-subscription

# security updates
deb http://security.debian.org/debian-security bullseye-security main contrib
```

# Fail2Ban
apt install fail2ban<br>
systemctl enable fail2ban<br>
systemctl start fail2ban

# Get CPU temperature
apt update && apt install lm-sensors hddtemp -y<br>
sensors-detect<br>
sensors

# Watchdog
Source: https://it-notes.dragas.net/2018/09/16/proxmox-enable-and-use-watchdog-to-reboot-stuck-servers/ \
config files, add:
```
cd /etc/pve/qemu-server
nano 101.conf
```
Add following line:
```
watchdog: model=i6300esb,action=reset
```

# Set to powersave mode
1. SSH to Proxmox.
2. In the shell, at the command prompt enter
To see the list of available CPU governor states:
* cat /sys/devices/system/cpu/cpu0/cpufreq/scaling_available_governors<br>
To check what you currently is running:<br>
* cat /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor
3. To enable a more power efficient state:
* echo "powersave" | tee /sys/devices/system/cpu/cpu*/cpufreq/scaling_governor
