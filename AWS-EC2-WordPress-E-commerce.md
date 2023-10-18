# AWS EC2 WordPress E-commerce Project

Welcome to my AWS repository showcasing a project for hosting an e-commerce website using WordPress, a LEMP (Linux, Nginx, MySQL, PHP) stack, and securing it with an SSL certificate.

![E-commerce Website](ecommerce.jpg)

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


2. **Install and Configure LEMP Stack**: Install and configure the LEMP stack components on your EC2 instance. You can follow our documentation in the [**LEMP-Installation-Guide**](LEMP-Installation-Guide.md) for detailed instructions.

3. **Install WordPress**: Install and configure WordPress on your EC2 instance. Create the necessary database, configure Nginx to serve your site, and install required plugins and themes.

4. **Secure with SSL**: Acquire an SSL certificate (e.g., Let's Encrypt) and configure Nginx to use SSL. This ensures a secure and encrypted connection for your e-commerce site.

5. **Customize Your Website**: Customize your WordPress website, add products, and configure your e-commerce platform according to your requirements.

6. **Launch Your E-commerce Site**: Once everything is set up, you're ready to launch your e-commerce website and start serving customers securely.

## Project Documentation

- [**LEMP-Installation-Guide.md**](LEMP-Installation-Guide.md): A step-by-step guide for installing and configuring the LEMP stack on your EC2 instance.

- [**WordPress-Setup-Guide.md**](WordPress-Setup-Guide.md): Instructions for installing and setting up WordPress on your server.

- [**SSL-Configuration-Guide.md**](SSL-Configuration-Guide.md): Detailed steps for securing your site with an SSL certificate.

## Contributions

Contributions to this project are welcome! If you find issues or have suggestions for improvements, please feel free to create an issue or submit a pull request.

## Contact

If you have any questions or need assistance, you can reach me at [jimmy.h.cao@gmail.com](mailto:jimmy.h.cao@gmail.com).

Enjoy building your e-commerce site on AWS! 🚀
