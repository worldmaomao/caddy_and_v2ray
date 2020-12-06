# caddy and v2ray

## 特性
1.支持websocket + v2ray

2.支持websocket + tls + v2ray 

3.支持站点伪装


## 原理：
1.v2ray前面，使用caddy做反向代理

2.使用caddy获取自动获取https证书（相当的简单）

## 需要修改的地方：
### 1）修改端口
只要修改docker-compose.yml文件里配置（"21312:8080"），21312。
修改21312为其他端口，:（冒号）后面的80不要修改。

### 2）修改域名
把Caddyfile里的 www.xxoo.com 域名改为你自己注册的域名

### 3）修改v2ray的uuid
修改v2ray/server.json文件里的配置（inbounds -> settings -> clients -> id）。

uuid的生成方式：

a)访问http://www.uuid.online/ 

b)cat /proc/sys/kernel/random/uuid

### 4）站点伪装
把静态网站的放到html文件夹里

## 启动方式：
1.安装好docker，docker-compose

2.执行命令: docker-compose up -d

## 附录

 - [debian/ubuntu docker和docker-compose安装指南](https://blog.csdn.net/weixin_43944305/article/details/103618539)
 - [centos 7 docker和docker-compose安装指南]( https://www.cnblogs.com/eternityz/p/13264980.html)

