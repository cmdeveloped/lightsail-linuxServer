## Linux Server Configuration

#### Server Information
###### IP: 52.91.66.177
###### Live: http://52.91.66.177
###### Accessible SSH port: 2200

##### Project Overview
This project teaches how to access, secure, and perform the initial configuration of a bare-bones Linux server through Amazon Web Service's Lightsail. We accomplish this by learning how to install and configure a web and database server, and actually hosting a web application already developed through the Udacity Full Stack Nanodegree Program.

##### Steps for Completion
1. Start a new Ubuntu Linux server instance on Amazon Lightsail.
2. SSH into your server on the web.
3. Update all currently installed packages.
4. Change the SSH port from 22 to 2200 & configure Lightsail networking settings to allow this change.
5. Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200/tcp), HTTP (port 80/tcp), and NTP (port 123/udp).
6. Create a new user account named **grader**.
7. Give **grader** permission to sudo.
8. Create an SSH key pair for **grader** on local machine using ssh-keygen.
9. Configure the local timezone to UTC.
10. Install and configure Apache to serve a Python mod_wsgi application.
11. Install and configure PostgreSQL.
12. Install git and clone Item Catalog project from Github repository.
13. Configure all settings on the server to allow viewing of said application when visiting the server's IP address in a browser.

##### Configurations
1. Update and Upgrade installed packages.
```
sudo apt-get update
sudo apt-get upgrade
sudo apt-get install finger
```
2. Create new user **grader** and grant permissions.
```
sudo adduser grader
sudo nano /etc/sudoers.d/grader

  # Add this to the file!
  grader ALL=(ALL:ALL) ALL
```
3. Configure the timezone.
```
sudo dpkg-reconfigure tzdata
```
4. Change the SSH port from 22 to 2200.
```
# Edit port line from 22 to 2200
sudo nano /etc/ssh/sshd_config
sudo service ssh restart
```
5. Configure the Uncomplicated Firewall (UFW)
```
sudo ufw allow 2200/tcp
sudo ufw allow 80/tcp
sudo ufw allow 123/udp
sudo ufw enable
```
6. Install Apache and Git
```
sudo apt-get install apache2 git

sudo apt-get install libapache2-mod-wsgi python-dev
sudo a2enmod wsgi
sudo service apache2 start

git config --global user.name cmdeveloped
git config --global user.email cmdeveloped@gmail.com
```


#### References
DigitalOcean: https://www.digitalocean.com/community/tutorials/how-to-deploy-a-flask-application-on-an-ubuntu-vps

Special thanks to [iliketomatoes](https://github.com/iliketomatoes/linux_server_configuration) for a very informative guide.
