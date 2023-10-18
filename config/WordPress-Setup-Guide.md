# WordPress Installation on Ubuntu with Nginx

Follow these steps to install WordPress on your Ubuntu server using Nginx as the web server. This guide includes setting up the database, configuring Nginx, and finishing the WordPress installation.

## Install WordPress

After connecting and installing the LEMP stack on our server as described previously, execute the following commands to install WordPress on Ubuntu.

```bash
cd /var/www
sudo wget https://wordpress.org/latest.tar.gz
sudo tar -xzvf latest.tar.gz
sudo rm latest.tar.gz
sudo chown -R www-data:www-data wordpress
sudo find wordpress/ -type d -exec chmod 755 {} \;
sudo find wordpress/ -type f -exec chmod 644 {} \;
```

## Database setup
At this point we will be securing our MariaDB installation by adding a password and disabling other features. After running the following command, create a password and when prompted, answer Y.

```bash
sudo mysql_secure_installation
```
Now we can access the MariaDB console with the password that we just created by running the command:

```bash
sudo mysql -u root -p
```

Within the MariaDB console, create a database for WordPress. Please choose your own database name, user name, and a password. For this project I just kept it simple using the database name <code>example_db</code> and the user <code>example_user</code>.

```bash
create database example_db default character set utf8 collate utf8_unicode_ci;
create user 'example_user'@'localhost' identified by 'example_pw';
grant all privileges on example_db.* TO 'example_user'@'localhost';
flush privileges;
exit
```


## Nginx Web Server Configuration
Navigate to the directory which contains configuration files for the Nginx web server, and create a new configuration file with the text editor of your choice (nano, vim, etc.)

```bash
cd /etc/nginx/sites-available/
sudo vim wordpress.conf
```


