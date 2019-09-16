# Apache Setup
Install from the repository
```
$ sudo yum install httpd
$ sudo systemctl start httpd
$ sudo systemctl enable httpd
```

### Rewrite Module
Add `LoadModule rewrite_module modules/mod_rewrite.so` to /etc/httpd/conf/httpd.conf

Test with `$ grep -i LoadModule /etc/httpd/conf/httpd.conf | grep rewrite`

Change AllowOverride None -> All
```config
<Directory /var/www/html> 
    ....
    AllowOverride All
    ...
</Directory>
```

### VirtualHost Setup
The following assumes magento's root directory is `/var/www/magento2/`

```
<VirtualHost *:80>
     ServerAdmin admin@domain.com
     DocumentRoot /var/www/magento2/
     ServerName domain.com
     ServerAlias www.domain.com

     <Directory /var/www/magento2/>
        Options Indexes FollowSymLinks MultiViews
        AllowOverride All
        Order allow,deny
        allow from all
     </Directory>

    ErrorLog /var/log/httpd/magento_error.log
    CustomLog /var/log/httpd/magento_access.log combined
</VirtualHost>
```

### Testing / enabling
To test configuration file is good use `$ apachectl configtest`

After making changes run `$ sudo systemctl restart httpd`


## Resources
General setup https://www.mageplaza.com/devdocs/how-install-magento-2-centos.html
Rewrite Module https://www.e2enetworks.com/help/knowledge-base/how-to-enable-mod_rewrite-on-apache-on-centos/
