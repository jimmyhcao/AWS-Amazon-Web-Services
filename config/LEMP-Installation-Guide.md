
# Connecting to Your EC2 Instance and Setting Up LEMP

In this guide, you'll learn how to connect to your AWS EC2 instance and set up the LEMP (Linux, Nginx, MySQL, PHP) stack. Follow the steps below to get started.

## Connect to Your EC2 Instance

1. From the AWS EC2 Dashboard, navigate to the "Instances" page.

2. Select your EC2 instance by clicking on it.

3. Click the "Connect" button on the instance details page.

 ![Connect to your instance](https://i.imgur.com/oO8Y63j.png)
 
4. In the "Connect to your instance" dialog, you'll see instructions for connecting to your instance. Follow the SSH client instructions for your operating system.
 
  ![SSH client instructions](https://i.imgur.com/qYT76wB.png)
  
## SSH Client (Linux/macOS):

1. Open your terminal.

2. Navigate to the directory where your key pair file is located.

3. Use the `chmod` command to set secure permissions for your key pair file (replace `your-key-pair.pem` with the actual name of your key pair file):

   ```bash
   chmod 400 your-key-pair.pem

## Update System and Install LEMP Packages

Now that you are connected to your EC2 instance, follow these commands to update the system and install the LEMP stack:

1. **Update the system:**

    ```bash
    sudo apt update
    sudo apt upgrade
    ```

2. **Install Nginx, MariaDB, PHP, and other necessary packages:**

    ```bash
    sudo apt install nginx mariadb-server php-fpm php-mysql
    ```


In this README, I've provided instructions for connecting to your EC2 instance, setting up key pair permissions, and executing the commands to update the system and install LEMP packages. Make sure to replace `your-key-pair.pem` with the actual name of your key pair file and `your-instance-ip` with your instance's public IP address.
