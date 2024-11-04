# Nginx Server Setup on Red Hat Linux

This guide provides step-by-step instructions for installing and configuring an Nginx server on Red Hat Linux. Follow these steps to set up Nginx and test its functionality.

## Table of Contents

- [Prerequisites](#prerequisites)
- [Installation Steps](#installation-steps)
- [Starting and Enabling Nginx](#starting-and-enabling-nginx)
- [Basic Configuration](#basic-configuration)
- [Testing the Nginx Server](#testing-the-nginx-server)
- [Troubleshooting](#troubleshooting)
- [Uninstalling Nginx](#uninstalling-nginx)

## Prerequisites

Ensure you have the following:
- A Red Hat Linux environment
- Sudo privileges

## Installation Steps

1. **Update System Packages**
   
   Update the system to ensure all packages are current:
   ```bash
   sudo yum update -y
    ```
   
## Install the EPEL Repository

Nginx is not included in the default Red Hat repositories, so we need to enable the EPEL (Extra Packages for Enterprise Linux) repository:

```bash
sudo yum install epel-release -y
```
## Install Nginx

Install the Nginx package:

```bash

sudo yum install nginx -y
```
## Starting and Enabling Nginx
To start the Nginx server and ensure it runs on startup, use the following commands:

```bash

sudo systemctl start nginx
sudo systemctl enable nginx
```
## Basic Configuration
Edit the Default Configuration File

The default configuration file is located at /etc/nginx/nginx.conf. You can modify it as needed:

```bash
sudo nano /etc/nginx/nginx.conf
```
Restart Nginx to Apply Changes

After making changes, restart Nginx:

```bash
sudo systemctl restart nginx
```
## Testing the Nginx Server
Check Nginx Status

## Verify that Nginx is running:

```bash
sudo systemctl status nginx
```
## Access Nginx in a Browser

Open a web browser and enter the server's IP address or localhost:

```bash
http://your_server_ip
```
If configured correctly, you should see the default Nginx welcome page.

## Troubleshooting
Check the Nginx Error Log

View the error log if Nginx encounters issues:

```bash
sudo tail -f /var/log/nginx/error.log
```
## Check Configuration Syntax

Ensure the configuration syntax is correct:

```bash
sudo nginx -t
```
## Uninstalling Nginx
To remove Nginx and its dependencies:

```bash
sudo yum remove nginx -y
```
