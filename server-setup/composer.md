# Composer Installation (including Magento)

## Install Composer
```
$ curl https://getcomposer.org/installer | php
$ sudo mv composer.phar /usr/local/bin/composer
$ sudo chmod +x /usr/local/bin/composer
```

## Install Magento
Get access keys from the [Magento Marketplace](https://marketplace.magento.com) ([guide](https://devdocs.magento.com/guides/v2.3/install-gde/prereq/connect-auth.html))

Add apache as a group to your current user
```
$ sudo usermod -a -G apache centos
```
Test with `$ groups centos`

Go to the docroot as configured in the vhost section of apache `/var/www/html/`
```
$ sudo chown centos:apache /var/www/html
$ cd /var/www/html
```

The following will install to a new folder `/var/www/html/magento2`
```
$ composer create-project --repository=https://repo.magento.com/ magento/project-community-edition magento2
```

Change the permissions
```
$ cd magento2
$ sudo find var generated vendor pub/static pub/media app/etc -type f -exec chmod g+w {} + && sudo find var generated vendor pub/static pub/media app/etc -type d -exec chmod g+ws {} + && sudo chown -R :apache . && sudo chmod u+x bin/magento
```

NOTE: Some of this needs a tidy up, there have been a few issues with permissions (apache needing to write stuff etc.), also with SFTP...
