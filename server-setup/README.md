# Server Setup (CentOS 7)
These are my notes on setting up a server. Install vim and **always check the firewall!**

## Order
Server setup to be completed in the following order:
1. Swap space (other notes)
2. Apache
3. PHP 7.2
4. MariaDB 10.1 / MySQL 5.6
5. Install Magento (Composer)


## Other Notes
### SELinux / Firewall
Try to check if your Centos 7 installation has SELinux installed use `$ sestatus`

If it is, disable it via `$ setenforce 0` (TBC - Module on configuring SELinux)

Remember to check the external firewall from cloud host (AWS Lightsail doesn't enable HTTPS by default)

### Swap space
Magento needs 2GB of memory for updates, create swap space if using a server with less than 2GB. The following creates a swap space with 3GB of memory
```
$ sudo dd if=/dev/zero of=/swapfile bs=500M count=6
$ chmod 600 /swapfile
$ mkswap /swapfile
$ swapon /swapfile
```
Test with `$ swapon -s` and enable at boot with
```
$ vim /etc/fstab
$ /swapfile swap swap defaults 0 0
```

## Resources

Swap Space https://aws.amazon.com/premiumsupport/knowledge-center/ec2-memory-swap-file/
