# Linux常用命令
## 1.查看所有端口
```
$ netstat -ntlp
```
## 2.查看指定端口（12181和9092）
```
$ netstat -tunlp|egrep "(12181|9092)"
```
## 3.开通防火墙端口（8080为端口，此方法重启服务器需要重新开通）
```
$ /sbin/iptables -I INPUT -p tcp --dport 8080 -j ACCEPT
```
## 4.运行jar包 带端口号后台启动（yuqing-Kafka.jar为包名，8088为指定端口）
```
$ java -jar *.jar
$ nohup java -jar *.jar >*.out &
$ nohup java -jar yuqing-Kafka.jar --server.port=8088  &
```
## 5.测试ip和port是否通
```
$ ping 60.166.20.130:6012
```
如果ping不通,有可能服务器是放ping的，再用telent测试
```
$ telnet 60.166.20.130 6012
```
如果进入空白控制台，则说明ip和6012端口是通的
## 6.解压文件
解压gz文件
```
$ tar zxvf zookeeper-3.4.6.tar.gz
```
解压zip文件
```
$ unzip filename.zip
```
## 7.修改系统时间
修改时间
```
$ date -s "20181227 12:10:10"
```
查看时间
```
$ date
```
## 7.关闭防火墙
centOS 6.5关闭防火墙步骤

关闭命令
```
$ service iptables stop
```
永久关闭防火墙
```
$ chkconfig iptables off
```
两个命令同时运行，运行完成后查看防火墙关闭状态
```
$ service iptables status
```

Centos 7.x关闭防火墙步骤   

取消了iptables, 用firewall关闭
```
$ systemctl stop firewalld.service
$ systemctl disable firewalld.service
```
## 8.查看磁盘和内存空间
磁盘空间
 ```
$ df -h
 ```
内存空间
 ```
$ free -h
 ```
## 9.重启服务器
```
$ shutdown -r now
```
## 10.杀死端口
```
$ kill -9 pid
```
## 11.允许运行sh格式文件
```
$ chmod +x  *.sh
```
