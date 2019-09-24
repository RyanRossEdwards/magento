# Changing Web Domain
Whether migrating the site or moving from a dev environment to a live environment...

### Magento Side
At `Stores -> Configuration -> General -> Web -> Base URLs` change the following
```
Base URL = http://domain.com/
Base Link URL = http://domain.com/
Secure Base URL = https://domain.com/
Secure Base Link URL = https://domain.com/
```

### Server Side
Make changes to `$ sudo vim /etc/httpd/conf/httpd.conf`

Use `:g/olddomain.com` to list all occurrences. 

Use `:%s/olddomain.com/domain.com/gc` to replace olddomain.com with domain.com (with confirmation).


### Notes on SSL Certs / HTTPS
May be a good idea setting `Use Secure URLs in Admin = No` if the site requires a new SSL certificate.

Other changes may be required to get it working.

See also `https.md` for more info.
