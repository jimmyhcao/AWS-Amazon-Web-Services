# SSL Certificate Installation Guide

This guide will help you secure your website with an SSL certificate from Let's Encrypt. SSL certificates enable HTTPS for your website, ensuring secure data transmission.

## Step 1: Install Snapd

```bash
sudo apt install snapd
```

This command installs Snapd, which is essential for managing snap packages, including Certbot.

## Step 2: Install Core and Certbot
```bash
sudo snap install core; snap refresh core
sudo snap install --classic certbot
```

These commands install Snap core and Certbot. Certbot is the tool we'll use to obtain and manage the SSL certificate.

## Step 3: Create a Symbolic Link

```bash
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```
This step creates a symbolic link for Certbot to make it easily accessible from the command line.

## Step 4: Obtain the SSL Certificate

```bash
sudo certbot --nginx
```

Run Certbot with the --nginx option to automatically configure Nginx for SSL and obtain the SSL certificate from Let's Encrypt. Follow the on-screen instructions to complete the certificate issuance process.

We have now secured our WordPress ecomernce site with a SSL certificate!

   ![certbot](https://i.imgur.com/Blb9iRg.png)
   ![certbot](https://i.imgur.com/5NQ73g1.png)

## Step 5: Update WordPress Settings
Certainly, here's a README.md for your GitHub repository detailing the steps to install an SSL certificate for HTTPS on your website using Let's Encrypt:

```markdown
# SSL Certificate Installation Guide

This guide will help you secure your website with an SSL certificate from Let's Encrypt. SSL certificates enable HTTPS for your website, ensuring secure data transmission.

## Step 1: Install Snapd

```bash
sudo apt install snapd
```

This command installs Snapd, which is essential for managing snap packages, including Certbot.

## Step 2: Install Core and Certbot

```bash
sudo snap install core; snap refresh core
sudo snap install --classic certbot
```

These commands install Snap core and Certbot. Certbot is the tool we'll use to obtain and manage the SSL certificate.

## Step 3: Create a Symbolic Link

```bash
sudo ln -s /snap/bin/certbot /usr/bin/certbot
```

This step creates a symbolic link for Certbot to make it easily accessible from the command line.

## Step 4: Obtain the SSL Certificate

```bash
sudo certbot --nginx
```

Run Certbot with the `--nginx` option to automatically configure Nginx for SSL and obtain the SSL certificate from Let's Encrypt. Follow the on-screen instructions to complete the certificate issuance process.

## Step 5: Update WordPress Settings

Finally, go to your WordPress administrator dashboard and follow these steps:

1. Navigate to "Settings" in the sidebar.
2. Click on "General."

In the "General" settings, locate "WordPress Address (URL)" and "Site Address (URL)." Update both URLs to start with "https://" to ensure that your WordPress site uses the secure HTTPS connection.

By following these steps, you'll have successfully secured your website with an SSL certificate and enabled HTTPS for your WordPress site. This ensures the safe and encrypted transmission of data between your site's visitors and your server.
