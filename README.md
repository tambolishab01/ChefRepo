# ChefRepo [DATA AGENDA PROJECT]

Write a cookbook to download jenkins war file and deploy it in Apache server with Jenkins port 8090 configured. 

reference:
you can download file from below location 
http://mirrors.jenkins.io/war-stable/2.89.4/

Server Details:

Chef Client: 
Server IP: 40.87.82.177
User Name: chefuser 
Password: chefuser@123

Target Server: 
Server IP: 137.117.109.98
User Name: ubuntu
Password: ubuntu@12345


-> Created Cookbook to download jenkins war file from the location http://mirrors.jenkins.io/war-stable/2.89.4/,apache tomact server installation and Jenkins deployed on same apache tomcat server.
both apache and jenkins listing on defualt port 8080

-> To configure Jenkins port 8090 we need to change apache configuration file i.e. we need to define 8090 port for jenkins in configuration file.


