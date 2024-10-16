# 后端部署步骤

## 1.切换release分支

（1）从github仓库上拉取后端仓库代码；

（2）通过```git checkout release``` 指令选择切换仓库分支。

![后端部署1](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B21.png?raw=true)

## 2.拉取最新版本代码

通过```git pull origin release```指令取后端代码仓库最新版本的代码。

![后端部署7](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B27.png?raw=true)

## 3.更新配置文件

将配置文件中的主机ip、用户名、密码换为HTG数据库的信息。

![后端部署2](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B22.png?raw=true)

## 4.构建jar包

（1）通过```mvn clean package```指令构建服务器上运行的后端代码jar格式文件（Java Archive，简称jar包）；

（2）确认target目录下jar包正常生成；

（3）使用``` jar包名称.jar ```指令在本地试运行jar格式文件；

（4）在本地测试后端程序是否部署完成。

![后端部署3](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B23.png?raw=true)

## 5.配置服务器环境

(1)连接浙江大学RVPN系统，并通过ssh命令进入到浙大云服务器中；

![后端部署4](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B24.png?raw=true)

（2）使用```java -version```指令检查是否安装Java，确认Java版本是否为1.8。

![后端部署5](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B25.png?raw=true)

若没有安装Java则需使用```sudo apt install openjdk-8-jre-headless```指令安装。

## 6.上传Jar包

（1）使用XFTP文件传输软件连接服务器；

（2）在指定路径下传入jar包。

![后端部署6](https://github.com/Christine1230/Users-Doc/blob/main/docs/source/image/%E5%90%8E%E7%AB%AF%E9%83%A8%E7%BD%B26.png?raw=true)

## 7.运行jar包

使用```jar包名称.jar```指令运行后端代码jar包文件。

