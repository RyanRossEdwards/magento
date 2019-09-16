# PHP 7.2 Setup

## Installing PHP 7.2
Currently 7.2 isn't in the default CentOS repos, following are considered [safe](https://wiki.centos.org/AdditionalResources/Repositories)

Install EPEL `$ sudo yum install epel-release`

Install Remi `$ sudo yum install http://rpms.remirepo.net/enterprise/remi-release-7.rpm`

### Using yum-utils
```
$ sudo yum install yum-utils
$ sudo yum-config-manager --enable remi-php72
$ sudo yum update
$ sudo yum install php
```

(Alternatively can use `$ sudo yum --enablerepo=remi-php72 install php`)

### Extensions

Install the required extensions:

`$ sudo yum install php-bcmath php-ctype php-curl php-dom php-gd php-hash php-iconv php-intl php-mbstring php-openssl php-pdo_mysql php-simplexml php-soap php-spl php-xsl php-zip php-libxml`

Test with `$ php -me`

Check Zend Engine is installed with `$ php -v`

## Configure PHP

Change the following in `$ sudo vim /etc/php.ini`
```
file_uploads = On
allow_url_fopen = On
short_open_tag = On
memory_limit = 512M
upload_max_filesize = 128M
max_execution_time = 3600
```

## Resources
General installation https://www.cyberciti.biz/faq/how-to-install-php-7-2-on-centos-7-rhel-7/

General installation https://tecadmin.net/install-php7-on-centos7/
