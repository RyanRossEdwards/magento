# Server Setup (CentOS 7)
These are my notes on setting up a server. **Always check the firewall!**

### SELinux / Firewall
Try to check if your Centos 7 installation has SELinux installed use `$ sestatus`

If it is, disable it via `$ setenforce 0` (TBC - Module on configuring SELinux)

Remember to check the external firewall from cloud host (AWS Lightsail doesn't enable HTTPS by default)
