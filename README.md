# Project: Linux Server Configuration

Linux Server Configuration is the seventh project built during completion of the [Udacity's](https://www.udacity.com/) Nanodegree program [Full Stack Web Developer](https://www.udacity.com/course/full-stack-web-developer-nanodegree--nd004). To learn how it was built, check [Configuring Linux Web Servers](https://www.udacity.com/courses/configuring-linux-web-servers--ud299) and [Linux Command Line Basics](https://www.udacity.com/courses/linux-command-line-basics--ud595).

## Server access

Server IP address is **52.39.191.19** and SSH is served on port **2200**. The only user authorized to access the server is **grader** and only with SSH key. It can be done with command like this (provide path to SSH key):  
`ssh -i ~/.ssh/udacity_key.rsa grader@52.39.191.19 -p 2200`

## Item Catalog

Project Item Catalog was refactored to use [PostgreSQL](https://en.wikipedia.org/wiki/PostgreSQL) instead of [SQLite](https://en.wikipedia.org/wiki/SQLite) and is served at http://catalog.praqtiq.com.

## Server configuration

System packages have been updated and additional paakages have been installed:
* postgresql
* python-psycopg2
* python-pip
* apache2
* libapache2-mod-wsgi
* git

Timezone is set to UTC.  
User **grader** is created with sudo privileges.  
SSH is served on port 2200.  
Only incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123) are allowed.  
Only SSH connections with SSH key are allowed.  
User **root** can not login.  
[Apache](https://en.wikipedia.org/wiki/Apache_HTTP_Server) is configured to use mod_wsgi.  

### Resources

 Timezone setup:  [askubuntu.com](http://askubuntu.com/questions/138423/how-do-i-change-my-timezone-to-utc-gmt)  
 Add sudo user: [askubuntucom](http://askubuntu.com/questions/7477/how-can-i-add-a-new-user-as-sudoer-using-the-command-line)  
 mod_wsgi (Apache): [Flask documentation](http://flask.pocoo.org/docs/0.12/deploying/mod_wsgi/)  
Apache setup: [Official documentation](https://httpd.apache.org/docs/2.4/)

### Additional Configuration

DNS is conifgured to use **catalog.praqtiq.com** for web server.  
Google API Console is configured to accept OAuth requests form catalog.praqtiq.com.  
