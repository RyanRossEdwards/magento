# Enabling https

## Certbot Instructions
Make sure the DNS settings points to the server
```
A Record  |  @  |  3.123.123.321
```
Go to [certbot](https://certbot.eff.org/lets-encrypt/centosrhel7-apache) and follow instructions!

Choose 'Yes' for redirecting all traffic to https.

## Troubleshooting 
#### Won't load https
Could be an infinite loop, but more likely it's a firewall. Check the Server's firewalls and the Host's firewalls (e.g. AWS lightsail won't allow access to 443 out of the box).

#### Locked out of admin
If `Use Secure URLs in Admin = Yes` is preventing access, fix through `$ mysql -u magento -p`
```sql
USE magento;
UPDATE core_config_data SET value = 0 WHERE path = 'web/secure/use_in_frontend';
UPDATE core_config_data SET value = 0 WHERE path = 'web/secure/use_in_adminhtml';
```
Clean the cache for changes to take effect
```
php ~/magento2/bin/magento cache:clean
```

If the web browser is sending it to https

Use Chrome, go to `chrome://net-internals/#hsts` and delete site, or switch to a new browser
