# Laravel-azure-VM-deployment-instructions
Summary:
In production, you only need to run npm run build to precompile your assets. You do not run npm run dev or php artisan serve in production.
Your web server (e.g., Nginx, Apache) serves the Laravel app and the precompiled assets from the public/build directory.
Optimize your Laravel app with commands like php artisan config:cache, php artisan route:cache, etc., for better performance.

## To install apache

```bash
apt update
```
```bash
apt install apache2 -y
```

## To install php
```bash
sudo apt install -y php php-curl libapache2-mod-php php-mbstring php-xmlrpc php-soap php-gd php-xml php-cli php-zip php-bcmath php-tokenizer php-json php-pear
```
## To install mariadb
```bash
sudo apt install mariadb-server
```
## if you want to secure mysql
```bash
sudo mysql_secure_installation
```
## To enable, Start and Status
```bash
sudo systemctl start mariadb
sudo systemctl enable mariadb
sudo systemctl status mariadb
```


## To install composer
```bash
curl -sS https://getcomposer.org/installer | php
```
```bash
sudo mv composer.phar /usr/local/bin/composer
```
```bash
cd /var/www/html
```

## To create project
```bash
composer create-project laravel/laravel <your_project_name_here>
```
```bash
cd <your_project_name_here>
```
```bash
chown www-data:www-data * -R
chown www-data:www-data .* -R
```
## to create apache configuration file
```bash
cd /etc/apache2/000-default.conf
```
```bash
vi 000-default.conf
```
or
```bash
cd /etc/apache2/sites-available
```
```bash
vi laravel.conf
```
## To enable and Disable
```bash
a2dissite 000-default.conf
```
```bash
a2ensite laravel.conf
```

## To restart apache
```bash
service apache2 restart
```
