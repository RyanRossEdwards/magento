# PhpStorm
PhpStorm is an IDE for working on PhP, students can get an education license for free.

## Setting Up PhpStorm (PS)

Archive the magento2 file (local/ server backup)
```
$ tar cvf magento2_archive.tar /var/www/html/magento2/
```

In PS create a blank project and connect to the server
`Tools -> Deployment -> Configuration`

Set root path to the doc root `/var/www/html/magento2` and deployment path to `/`

### Downloading files

This was a terrible way (took hours):

Download the magento files with `Tools -> Deployment -> Download from server`

Next time sftp the archive and extract it in the PS project folder.

### Setup SQL

(to do - set up sql within php storm)

## Resources

Server Configuration https://www.jetbrains.com/help/phpstorm/creating-a-remote-server-configuration.html


