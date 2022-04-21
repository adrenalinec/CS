# docker 基本命令



| docker rm $(docker ps -aq)   | 删除全部容器 |      |
| ---------------------------- | ------------ | ---- |
| docker exec -it <ID> /bin/sh | 进入容器     |      |
|                              |              |      |
|                              |              |      |









# docker 没有工具怎么办



- cat /proc/version 查看linux版本

- cat /etc/issue \m



Alphine Linux 怎么安装软件

|            |      |      |
| ---------- | ---- | ---- |
| Apk update |      |      |
| apk add    |      |      |
|            |      |      |











# docker network 配置



```bash
#docker network create

#普通命令
docker network create --driver bridge --subnet 192.168.0.0/16 \
--gateway 192.168.0.1 turbonet

docker network breate --driver=bridge --subnet=192.168.0.0/16 \
--gateway=192.168.0.1 






```









# 基于Docker 的WP

## 基本框架



- wordpress 包
- mysql包









## 代码配置



```yml
version: '3.1'

services:

  wordpress:
    image: wordpress
    restart: always
    ports:
      - 8080:80
    environment:
      WORDPRESS_DB_HOST: turbodb
      WORDPRESS_DB_USER: turbouser
      WORDPRESS_DB_PASSWORD: turbopass
      WORDPRESS_DB_NAME: turbodb
    volumes:
      - wordpress:/var/www/html

  turbodb:
    image: mysql:5.7
    restart: always
    environment:
      MYSQL_DATABASE: turbodb
      MYSQL_USER: turbouser
      MYSQL_PASSWORD: turbopass
      MYSQL_RANDOM_ROOT_PASSWORD: '1'
    volumes:
      - db:/var/lib/mysql

volumes:
  wordpress:
  db:
```

















## Attention



- wordpress文件中wp-config.php是配置数据库的文件, 报错可以去这里查看是否配置正确
- Mysql中 mysql -u user -p 然后输入密码, 进入数据库, SHOW_DATABASES; 可以查看数据库是否建立成功









## 能够访问的几道墙

1. 云主机有安全组
2. 系统的防火墙, ubuntu默认不开启
3. Docker的端口映射是否打通



## docker 网络通信配置



```bash
配置网络

docker network create --driver bridge --subnet 192.168.0.0/16 \
--gateway 192.168.0.1 turbonet
```





## Mysql 启动配置(docker-compose)

```yml
version: '3.1'
  
services:
  mysql01:
    image: mysql:5.7
    restart: always
    ports:
      - 3306:3306
    environment:
      MYSQL_DATABASE: turbodb
      MYSQL_USER: turbo
      MYSQL_PASSWORD: turbo
      MYSQL_RANDOM_ROOT_PASSWORD: '1'
		

 
```



## Typecho 启动

```bash
docker run -d \
--name=typecho-blog \
--restart always \
--mount type=tmpfs,destination=/tmp \
-v /srv/http/typecho:/data \
-e PHP_TZ=Asia/Shanghai \
-e PHP_MAX_EXECUTION_TIME=600 \
-p 80:80 \
--network turbonet \
80x86/typecho:latest

#配置typecho

docker run -d -p 80:80 --name typecho01 --network turbonet -v /home/ubuntu/cc:/data 3437f7346b4c
```







## 修改Docker 端口

```shell
systemctl stop docker			#docker必须先停止, docker ps等所有docker命令都会启动docker
cd /var/lib/docker/container/[ID]
docker ps 								#查看ID和端口
vim hostconfig.json				#修改.json 和config.v2.json 文件
													#修改HostPort的端口号
```









## Nginx配置SSL 反向代理



```shell
										#直接修改/etc/nginx/conf.d 里面touch个.conf都可以
server {
	listen 80;
	return 301 https://turbofinance.top$request_uri;
}

server {
	listen 443 ssl;
	server_name turbofinance.top;
  ssl_certificate /etc/nginx/cert/turbo/turbofinance.top_bundle.crt;
  ssl_certificate_key /etc/nginx/cert/turbo/turbofinance.top.key;
  ssl_session_timeout 5m;
  ssl_protocols TLSv1 TLSv1.1 TLSv1.2;
  ssl_ciphers HIGH:!aNULL:!MD5;
  ssl_prefer_server_ciphers on;
	location / {
		proxy_set_header host $host;
		proxy_set_header X-Real-IP $remote_addr;
		proxy_set_header X-Forwarded-For $proxy_add_x_forwarded_for;
		proxy_pass http://turbofinance.top:8080/;
}
```











# 增加其他配置到Docker上





















## TTRSS







## RSSHub





















