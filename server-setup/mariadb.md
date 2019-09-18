# MariaDB 10.1 Setup
As Magento requires MySQL 5.6 or 5.7, MariaDB 10.1 (==5.6) or later is required.

### Installation steps
Note when doing the setup, I originally installed MariaDB 5.5, will need tidying up...

```
$ sudo yum install mariadb-server
```
```
$ sudo systemctl enable mariadb
$ sudo systemctl start mariadb
```
Note that commands for mysql relate to mariadb, following hardens the installation
```
$ sudo mysql_secure_installation
```

### Setting up Magento DB and User
Connect to mysql using root
```
sudo mysql -u root -p
```
Use the following SQL Queries to create the DB and User (repalce 'YOUR_PASSWORD')
```sql
CREATE DATABASE magento;
CREATE USER 'magento' IDENTIFIED BY 'YOUR_PASSWORD';
GRANT ALL ON magento.* TO 'magento' IDENTIFIED BY 'YOUR_PASSWORD' WITH GRANT OPTION;
FLUSH PRIVILEGES;
EXIT;
```

### Upgrading to MariaDB 10.1
(Section needs tidying up / resources)
```
$ yum localinstall https://dev.mysql.com/get/mysql57-community-release-el7-9.noarch.rpm
```
Change `$ sudo vim /etc/yum.repos.d/MariaDB.repo` to the following:
```
[mariadb]
name = MariaDB
baseurl = http://yum.mariadb.org/10.1/centos7-amd64
gpgkey=https://yum.mariadb.org/RPM-GPG-KEY-MariaDB
gpgcheck=1
```

## Resources

MariaDB comparability with MySQL https://mariadb.com/kb/en/library/mariadb-vs-mysql-compatibility/
