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

### Stack
* OS: Debian Wheezy 7.5
* HTTP server: Apache 2.2.22
* PHP: mod_php 5.5.13-1~dotdeb.1
* DB: MySQL 5.5
* XDebug
* Xhprof
* Mailcatcher 0.5.12

### Usage
* IP: 192.168.42.101
* Vhost: dev.dolibarr.org
* Root user: root
* Root password: root
* Configured DB users:
	* user/user for db dolibarr
	* root/root
* Initial dolibarr data: dev/initdata/mysqldump_dolibarr-3.5.0.sql

#### Mailcatcher
Configure Dolibarr to send all emails through SMTP 127.0.0.1 with port 1025 with user admin and no password.
You can access MailCatcher to read all outgoing emails at http://192.168.42.101:1080
