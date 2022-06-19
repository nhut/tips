# Update Proxmox
apt update && apt upgrade -y && apt dist-upgrade -y

# Remove Proxmox Subscription Notice
sed -Ezi.bak "s/(Ext.Msg.show\(\{\s+title: gettext\('No valid sub)/void\(\{ \/\/\1/g" /usr/share/javascript/proxmox-widget-toolkit/proxmoxlib.js && systemctl restart pveproxy.service

# Use no subsciption repository
https://pve.proxmox.com/wiki/Package_Repositories#sysadmin_no_subscription_repo
