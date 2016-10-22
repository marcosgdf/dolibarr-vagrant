dolibarr-vagrant
================

Vagrant machine configured for Dolibarr development built with [PuPHPet](http://www.puphppet.com)

### How to use
Mimic the following directory structure

```
|
\-- dolibarr (your copy of dolibarr project)
\-- dolibarr-vagrant (your copy of dolibarr-vagrant project)
```

Now you are ready to start you Vagrant machine.

Remember to update the OS regularly and to add the vhost `dolibarr.local` to your hosts file. [How?](http://en.wikipedia.org/wiki/Hosts_%28file%29#File_content)

After Puppet provision, you must reboot MySQL service so that the strict mode gets applied. To do so:
```
1. vagrant ssh
2. sudo service mysql restart
```

### Stack
* OS: Ubuntu 16.04.1 LTS
* 512 MB
* HTTP server: Apache/2.4.23 (Ubuntu)
* PHP: 5.6.27-1+deb.sury.org~xenial+1
* DB:
	* MySQL 5.7.16 MySQL Community Server (GPL)
	* PostgreSQL 9.6.0 (remember to follow this tutorial https://gist.github.com/ffmike/877447 after provisioning the VM)
* XDebug
* Xhprof
* Mailhog
* Composer
* Adminer 4.2.4

### Usage
* IP: 192.168.42.101
* Vhost: dolibarr.local
* Root user: root
* Root password: root
* MySQL:
	* user/user for db dolibarr
	* root/root
	* Initial dolibarr data: dev/initdata/mysqldump_dolibarr-3.8.0.sql
* PostgreSQL:
	* postgres/123
	
#### DB access
DB connections outside the machine are not allowed. You must connect through a SSH tunnel. You can find the private key for vagrant user in puphpet/files/dot/ssh/id_rsa

#### Mailhog
You can access Mailhog to read all outgoing emails at http://192.168.42.101:8025

#### Adminer
Adminer is a DB web client. You can access it through http://192.168.42.101/adminer/

#### XHProf
XHProf is a function-level hierarchical profiler for PHP. You can access it through http://192.168.42.101/xhprof/xhprof_html/
