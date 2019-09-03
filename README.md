### 操作系统 Centos7.x

### web 服务器: Nginx1.16.1
配置文件: /etc/nginx/nginx.conf

站点配置: /etc/nginx/conf.d/

端口:80

日志: /var/log/nginx/

### 数据库: mysql 5.6.45
存储路径: /data/mysql

配置文件: /etc/my.cnf

端口:3306

日志: /var/log/mysqld.log

密码存放: /credentials/password.txt


### 缓存: redis3.2.12
配置文件: /etc/redis.conf

端口: 6379(不需要开放)

日志: /var/log/redis/redis.log



### open-falcon 部分:

open-falcon 程序主体路径 : /data/open-falcon

配置文件:

falcon-aggregator: /data/open-falcon/aggregator/config/cfg.json

falcon-graph: /data/open-falcon/graph/config/cfg.json

falcon-hbs: /data/open-falcon/hbs/config/cfg.json

falcon-nodata: /data/open-falcon/nodata/config/cfg.json

falcon-api: /data/open-falcon/api/config/cfg.json

falcon-alarm: /data/open-falcon/alarm/config/cfg.json

falcon-dashboard: /data/open-falcon/dashboard/rrd/config.py  /data/open-falcon/dashboard/gunicorn.conf

日志文件:
falcon-aggregator: /var/log/messages

falcon-graph: /var/log/messages

falcon-hbs: /var/log/messages

falcon-nodata: /var/log/messages

falcon-api: /var/log/messages

falcon-alarm: /var/log/messages
falcon-dashboard: /var/log/messages


端口:(根据需求开发,镜像不需要)
|端口|服务|
|--|--|
|16060 |falcon-gateway| 
|4444  |falcon-transfe| 
|6080  |falcon-judge|   
|18433 |falcon-gateway| 
|6081  |falcon-judge|   
|1988  |falcon-agent|   
|6055  |falcon-aggrega| 
|6090  |falcon-nodata|  
|14444 |falcon-gateway| 
|6060  |falcon-transfe| 
|6030  |falcon-hbs|     
|6031  |falcon-hbs|     
|8080  |falcon-api|     
|8433  |falcon-transfe| 
|6070  |falcon-graph|   
|6071  |falcon-graph|   
|9912  |falcon-alarm|   
|8081  |falcon-dashboard|

命令行工具:
1. `/data/open-falcon/open-falcon`
   ```
   Usage:
      open-falcon [flags]
      open-falcon [command]

    Available Commands:
      check       Check the status of Open-Falcon modules
      help        Help about any command
      monitor     Display an Open-Falcon module's log
      reload      Reload an Open-Falcon module's configuration file
      restart     Restart Open-Falcon modules
      start       Start Open-Falcon modules
      stop        Stop Open-Falcon modules

    Flags:
      -v, --version   show version

    Use "open-falcon [command] --help" for more information about a command.

   ```

####服务 
```
systemctl restart falcon-aggregator
systemctl restart falcon-graph
systemctl restart falcon-hbs
systemctl restart falcon-nodata
systemctl restart falcon-api
systemctl restart falcon-alarm
systemctl restart falcon-dashboard
systemctl restart falcon-judge
systemctl restart falcon-transfer
systemctl restart falcon-agent
systemctl restart falcon-gateway
systemctl restart nginx
systemctl restart redis
systemctl restart mysql
```

### 安装方式:
Github 下载二进制安装

### 访问方式:
IP访问


### 用户名/密码 
IP访问后注册