# 前端部署步骤

## 1.安装依赖库

在服务器中安装依赖库，指令``` npm install ```。

## 2.生成build文件

通过指令``` npm run build ``` 生成build文件，生成的dist文件夹位于 /build文件夹下。

![前端部署1.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B21.png?raw=true)

## 3.配置服务器环境

连接浙江大学RVPN系统，并通过ssh命令进入到浙大云服务器中

![前端部署2.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B22.png?raw=true)

## 4.配置Nginx代理服务

Nginx 作为代理服务器，能够将前端的请求转发给后端，并接受来自后端的返回

(1)使用 ``` apt-get install nginx ``` 指令,安装Nginx代理服务；

![前端部署3.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B23.png?raw=true)

(2)等待其安装依赖库以及Nginx本体；

(3)更改 /etc/nginx中的 nginx.conf 为项目build文件夹中的nginx.conf文件；

(4)保存服务器更改。

![前端部署4.png)](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B24.png?raw=true)

## 5.配置Build文件

(1)进入到usr/share/nginx/build/文件夹中；

(2)将之前build好的dist文件夹放入其中。

![前端部署5.png](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B25.png?raw=true)

## 6.运行Nginx服务器

(1)使用```  nginx -t  ```命令检查nginx.conf的语法是否正确；

![前端部署6](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B26.png?raw=true)

(2)使用``` systemctl start nginx ``` 启动nginx服务器，如果已经启动，可用``` systemctl reload nginx ```来重启动；

![前端部署7](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B27.png?raw=true)

(3)使用``` systemctl status nginx ```检查nginx服务器，若显示usr/sbin/nginx的字样即代表正常运行。

![前端部署8](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B28.png?raw=true)

## 7.检查80端口是否正常挂载

(1)运行``` netstat -anp |grep :80 ```指令查看80端口运行情况，如果“0.0.0.0.0:80”对应为Nginx则服务正常；

![前端部署9](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%89%8D%E7%AB%AF%E9%83%A8%E7%BD%B29.png?raw=true)

(2)登录前端服务器地址查看前端服务是否正常启动。如果依然无法正常启动，采用```systemctl stop firewalld```指令关闭防火墙。
