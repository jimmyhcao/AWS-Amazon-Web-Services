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

## Database Setup
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
Navigate to the directory which contains configuration files for the Nginx web server.

```bash
cd /etc/nginx/sites-available/
```







Verify what version of PHP is on your server in the <code>/var/run/php</code> directory. For me, I am running PHP 8.1.

![php version](https://i.imgur.com/Ty1S4ey.png)


Keeping the PHP version in mind, create a new configuration file with the text editor of your choice (nano, vim, etc.)

```bash
sudo nano wordpress.conf
```


Now we can use this configuration template for our website:

```bash
upstream php-handler {
        server unix:/var/run/php/php8.1-fpm.sock;
}
server {
        listen 80;
        server_name jimmys-lab.com www.jimmys-lab.com;
        root /var/www/wordpress;
        index index.php;
        location / {
                try_files $uri $uri/ /index.php?$args;
        }
        location ~ \.php$ {
                include snippets/fastcgi-php.conf;
                fastcgi_pass php-handler;
        }
}
```

<b>upstream php-handler</b>: This section defines the backend PHP handler that communicates with PHP-FPM. It specifies the location of the PHP-FPM socket file, which is used to process PHP scripts. In this case, it's pointing to a PHP 7.4 FPM socket.

<b>server</b>: This block defines the server configuration for handling requests to the specified server name and port.

<b>listen 80</b>: This line specifies that Nginx should listen on port 80 for HTTP requests.

<b>server_name</b>: This line specifies the server name(s) for which this server block should handle requests. In this case, it's "jimmys-lab.com" and "www.jimmys-lab.com."

<b>root /var/www/wordpress</b>: The <b>root</b> directive sets the root directory for this server block, which is the directory where the WordPress files are located.

<b>index index.php</b>: This line sets the default index file to "index.php."

<b>location /</b>: This block defines how Nginx should handle requests for the root directory ("/") and attempts to serve WordPress content using "index.php" when necessary.

<b>location ~ \.php$</b>: This block is used to handle PHP files. It includes a configuration file for fastcgi and passes requests to the PHP handler defined in the <b>upstream</b> block, which uses the PHP 7.4 FPM socket for processing PHP scripts.


Next, create a symbolic link to inform Nginx about your website, test configuration, and then implement the modifications by restarting the web server.

```bash
sudo ln -s /etc/nginx/sites-available/wordpress.conf /etc/nginx/sites-enabled/
sudo nginx -t
sudo systemctl restart nginx
```
![symbolic link](https://i.imgur.com/ZF6ozr0.png)


## Wrapping Up WordPress Install
By now our DNS propagation should have completed. We can finish installing WordPress by navigating to our domain name in a web browser. From here we will be prompted to log in using the credentials we created earlier during the <b>Database Setup</b> step



















