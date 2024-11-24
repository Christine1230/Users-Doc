# Deployment Procedure

The HTG database is deployed on the Zhejiang University cloud server platform in the mode of front-end and back-end separation. This section describes the front-end deployment process and back-end deployment process of the HTG database system. 

 

## Front-end deployment procedure

 

**(1)** ***\*Install the dependency library\****: Install the dependency library on the server, run the ‘’`npm install`‘’ command.

**(2)** ***\*Generate build file\****: Generate build file by command "`npm run build`", and the generated dist folder is located under /build folder.

![前端部署1.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B21.png?raw=true)

**(3)** ***\*Configure the server environment\****: Connect to the RVPN system of Zhejiang University, and enter the cloud server of Zhejiang University through ssh command. 

![前端部署2.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B22.png?raw=true)

**(4)** ***Configure Nginx proxy service\***: Nginx, as a proxy server, can forward requests from the front end to the back end, and accept the return from the back end. 

a. Run the ‘’`apt-get install nginx`‘’ command to install the Nginx agent service;

![前端部署3.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B23.png?raw=true)

b. Wait for it to install the dependency library and Nginx ontology; 

c. Change nginx.conf in /etc/nginx to the nginx.conf file in the build folder of the project; 

d. Save the server changes. 

![前端部署4.png)](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B24.png?raw=true)

**(5)** ***\*Configure the Build file\****: 

a. Go to the usr/share/nginx/build/ folder;

b. Put the dist folder built before into it. 

![前端部署5.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B25.png?raw=true)

**(6)** ***\*Run the nginx server\****:

a. Run the "`nginx-t`" command to check whether the syntax of nginx.conf is correct;

![前端部署6](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B26.png?raw=true)

b. Run ‘’`systemctl start nginx`’‘ to start the Nginx server. If the NginX server is already started, run the ’‘`systemctl reload nginx`’‘ command to restart it;

![前端部署7](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B27.png?raw=true)

c. Run the ’‘`systemctl status nginx`’‘ command to check the nginx server. If usr/sbin/nginx is displayed, it indicates that the nginX server is running properly. 

![前端部署8](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B28.png?raw=true)

**(7)** ***\*Check whether port 80 is mounted properly\****: 

a. Run the ’‘`netstat-anp |grep :80`’‘ command to check the running status of port 80. If 0.0.0.0.0:80 corresponds to Nginx, the service is running properly;

![前端部署9](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B29.png?raw=true)

b. Log in to the front-end server address to check whether the front-end service is started properly. If the firewall still fails to start, run the ’‘`systemctl stop firewalld`’‘ command to shut down the firewall. 

 

 

## Back-end deployment procedure

 

**(1)** ***\*Switch the release branch\****:

a. Pull up the backend repository code from the github repository; 

b. Run the ''`git checkout release` '' command to switch warehouse branches. 

![后端部署1](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B21.png?raw=true)

**(2)** ***\*Pull the latest version of the code\****: pull the latest version of the code of the back-end code warehouse through the "`git pull origin release`" command. 

![后端部署7](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B27.png?raw=true)

**(3)** ***\*Update the configuration file\****: Change the host ip address, user name, and password in the configuration file to the HTG database information. 

![后端部署2](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B22.png?raw=true)

**(4)** ***\*Build jar package\****: 

a. Build the back-end code jar format file (JavaArchive, referred to as jar package) running on the server through the "`mvn clean package`" instruction; 

b. Ensure that the jar package in the target directory is generated properly;

c. Run the ''`jar package's name.jar`'' command to run the jar file locally; 

d. Locally test whether the back-end program is deployed. 

![后端部署3](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B23.png?raw=true)

**(5)** ***\*Configure the server environment\****: 

a. Connect to the RVPN system of Zhejiang University, and enter the cloud server of Zhejiang University through ssh command; 

![后端部署4](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B24.png?raw=true)

b. Run the ''`java-version`'' command to check whether Java is installed and whether the Java version is 1.8. If Java is not installed, run the ''`sudo apt install openjdk-8-jre-headless`'' command to install it. 

![后端部署5](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B25.png?raw=true)

**(6)** ***\*Upload the jar package\****:

a. Connect to the server using the Xftp file transfer software;

b. Pass the jar package to the specified path. 

![后端部署6](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B26.png?raw=true)

**(7) \*Run the jar package***: Run the back-end code jar package file using the "`jar package's name.jar`" command.
