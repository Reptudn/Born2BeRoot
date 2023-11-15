## Installation
- install lighttpd with: `sudo apt-get install lighttpd`
	- enable service with `sudo systemctl enable lighttpd`
- install mariadb ([Wiki](https://www.digitalocean.com/community/tutorials/how-to-install-mariadb-on-ubuntu-20-04)): `sudo apt-get install mariadb-server`
	- setup with `sudo mysql_secure_installation`
	- start service: `sudo systemctl start mariadb.service`
	- check status: `sudo systemctl status mariadb`
- install PHP 🤮: `sudo apt-get install php`

Followed this tutorial:
[Wordpress Installation with lighttpd](https://www.osradar.com/install-wordpress-with-lighttpd-debian-10/)
## Database
- access MariaDB command line: `sudo mysql -u root -p`
- Privileges to `wordpress_user@localhost `and with pass `wordpress_pss123`
- wordpress folder is `/var/www/html/wordpess.jkauker.lan`

## Page
- page title: `jkauker42 wordpress page`
- username: `jkauker42`
- password: `ibims1wordpress!`