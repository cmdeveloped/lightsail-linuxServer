## Linux Server Configuration

##### Project Overview
This project teaches how to access, secure, and perform the initial configuration of a bare-bones Linux server through Amazon Web Service's Lightsail. We accomplish this by learning how to install and configure a web and database server, and actually hosting a web application already developed through the Udacity Full Stack Nanodegree Program.

##### Steps for Completion
1. Start a new Ubuntu Linux server instance on Amazon Lightsail.
2. SSH into your server on the web.
3. Update all currently installed packages.
4. Change the SSH port from 22 to 2200 & configure Lightsail networking settings to allow this change.
5. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200/tcp), HTTP (port 80/tcp), and NTP (port 123/udp).
6. Create a new user account named **Grader**.
7. Give **Grader** permission to sudo.
8. Create an SSH key pair for **Grader** on local machine using ssh-keygen.
9. Configure the local timezone to UTC.
10. Install and configure Apache to serve a Python mod_wsgi application.
11. Install and configure PostgreSQL.
12. Install git and clone Item Catalog project from Github repository.
13. Configure all settings on the server to allow viewing of said application when visiting the server's IP address in a browser.

#### Server Information
###### IP: 52.91.66.177
###### Live: http://52.91.66.177
###### Accessible SSH port: 2200

#### References
DigitalOcean: https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps
Thanks to [iliketomatoes](https://github.com/iliketomatoes/linux_server_configuration) for a very helpful README.
