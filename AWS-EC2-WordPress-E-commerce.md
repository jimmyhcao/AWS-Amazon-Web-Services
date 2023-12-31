# AWS EC2 WordPress E-commerce Project

Welcome to my AWS repository showcasing a project for hosting an e-commerce website using WordPress, a LEMP (Linux, Nginx, MySQL, PHP) stack, and securing it with an SSL certificate.

<p align="center">
  <img src="https://i.imgur.com/2j5TJFh.png" width="500" alt="AWS Logo">
</p>


## Project Overview

This project demonstrates how to set up a robust and secure e-commerce website using AWS services. It includes the following key components:

1. **EC2 Instance**: We leverage Amazon Elastic Compute Cloud (EC2) to deploy a virtual server for hosting the e-commerce site. This instance will run the LEMP stack.

2. **WordPress**: The website's front-end and content management system are powered by WordPress, providing a user-friendly interface for managing products, orders, and content.

3. **LEMP Stack**: The server is configured with the Linux operating system, Nginx web server, MySQL database, and PHP, creating a robust and high-performance hosting environment.

4. **SSL Certificate**: We secure the website using an SSL certificate, providing HTTPS encryption for customer data and improving trust.

## How to Use This Project

To get started with this project, follow these steps:

1. **Launch an EC2 Instance**: Use AWS EC2 to launch an instance. Make sure to select an appropriate instance type, configure security groups, and set up key pair authentication.

For this simple project, I used Ubuntu Server 22.04 LTS with a t2.micro instance. Organizations may require larger instances depending on their organizational needs. A key pair is also generated for secure login; ensure that the key is not shared so that others cannot log in. I will be using the default Virtual Private Cloud (VPC) with the only change in configuration being to the security group to allow HTTP and HTTPS traffic.

![Launch EC2 Instance](https://i.imgur.com/8C48l4g.png)
![Launch EC2 Instance](https://i.imgur.com/gpdPlZ9.png)
![Launch EC2 Instance](https://i.imgur.com/RWGqUq2.png)


2. **Associate Elastic IP and Configure DNS with Route 53**: Ensure your EC2 instance has a stable public IP address by associating an Elastic IP. Then, set up domain management using Amazon Route 53 for secure and reliable DNS resolution.

   ![Elastic IP](https://i.imgur.com/NpbYUdN.png)
   ![Route 53](https://i.imgur.com/IdBbCXx.png)

3. **Install and Configure LEMP Stack**: Install and configure the LEMP stack components on your EC2 instance. You can follow our documentation in the [**LEMP-Installation-Guide**](config/LEMP-Installation-Guide.md) for detailed instructions.

4. **Install WordPress**: Install and configure WordPress on your EC2 instance. Create the necessary database, configure Nginx to serve your site, and install required plugins and themes.

5. **Secure with SSL**: Acquire an SSL certificate (e.g., Let's Encrypt) and configure Nginx to use SSL. This ensures a secure and encrypted connection for your e-commerce site.

6. **Customize Your Website**: Customize your WordPress website, add products, and configure your e-commerce platform according to your requirements.

For this project I used the WooCommerce plug in with a store front theme. You can refer to the following videos for guidance on how to set up plug ins and themes on WordPress:
<li><a href="https://www.youtube.com/watch?v=W2zgKUFJflE" target="_blank">Plugins</a>

<li><a href="https://www.youtube.com/watch?v=8v6VARvAjFE" target="_blank">Themes</a></li><br>

7. **Launch Your E-commerce Site**: Once everything is set up, you're ready to launch your e-commerce website and start serving customers securely.

## Project Documentation

- [**LEMP-Installation-Guide.md**](config/LEMP-Installation-Guide.md): A step-by-step guide for installing and configuring the LEMP stack on your EC2 instance.

- [**WordPress-Setup-Guide.md**](config/WordPress-Setup-Guide.md): Instructions for installing and setting up WordPress on your server.

- [**SSL-Configuration-Guide.md**](config/SSL-Configuration-Guide.md): Detailed steps for securing your site with an SSL certificate.


<br>

## Final Project
After going through all configurations, this is what the landing page looks like. This is a very simplistic ecommerce website hosted on AWS; future projects will build upon this instance.


![E-commerce Website](https://i.imgur.com/G1ilhhx.png)

## Contributions

Contributions to this project are welcome! If you find issues or have suggestions for improvements, please feel free to create an issue or submit a pull request.

## Contact

If you have any questions or need assistance, you can reach me at [jimmy.h.cao@gmail.com](mailto:jimmy.h.cao@gmail.com).

Enjoy building your e-commerce site on AWS! 🚀
