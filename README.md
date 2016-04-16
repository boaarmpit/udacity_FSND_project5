# Udacity Full Stack Nanodegree project 5
*Project 5 of the Udacity Full Stack Nanodegree (setting up a server and hosting Project 3)*

## Access instructions for reviewer
View the hosted site at http://ec2-52-25-30-35.us-west-2.compute.amazonaws.com/  
Access the server via ssh with the privately supplied rsa key at grader@52.25.30.35 port 2200  

## Configuration notes
The following changes were made to the server:  
- Update all currently installed packages  
- Change the SSH port from 22 to 2200  
- Configure the Uncomplicated Firewall (UFW) to only allow incoming connections for SSH (port 2200), HTTP (port 80), and NTP (port 123)  
- Install and configure Apache to serve a Python mod_wsgi application  
- Install and configure PostgreSQL (to not allow remote connections)
- Create a new user named catalog that has limited permissions (and also disable default postgres user)
- Install git, clone and setup the Catalog App project from [Project 3](https://github.com/boaarmpit/udacity_FSND_project3) (required updating google and facebook oauth settings, and configuring static file uploads)
- Install python-pip, python-psycopg2 and the following python libraries (requests, oauth2client, sqlalchemy, flask)
- Setup /etc/hostname and /etc/hosts


## Resources used  
Server settings:  
https://help.ubuntu.com/community/Sudoers  
http://askubuntu.com/questions/115151/how-to-setup-passwordless-ssh-access-for-root-user  
https://help.ubuntu.com/community/UFW  

Apache/mod_wsgi  
https://www.digitalocean.com/community/tutorials/how-to-configure-the-apache-web-server-on-an-ubuntu-or-debian-vps
http://flask.pocoo.org/docs/0.10/deploying/mod_wsgi/  

Postgresql:  
http://www.postgresql.org/docs/9.3/static/auth-pg-hba-conf.html
http://askubuntu.com/questions/256534/how-do-i-find-the-path-to-pg-hba-conf-from-the-shell  
http://www.techonthenet.com/postgresql/grant_revoke.php  
http://www.postgresql.org/docs/8.2/static/sql-alterrole.html  

Google/Facebook:  
https://console.developers.google.com/home/dashboard  
https://developers.facebook.com/apps  

Other:  
http://askubuntu.com/questions/59458/error-message-when-i-run-sudo-unable-to-resolve-host-none  
http://askubuntu.com/questions/358867/how-to-view-the-bash-history-file-via-command-line  

#### Other notes:
Useful for checking python errors in log: `sudo tail -f /var/log/apache2/error.log | grep -Po --line-buffered '(?<=\:[0-9]{5}\]).*'`
