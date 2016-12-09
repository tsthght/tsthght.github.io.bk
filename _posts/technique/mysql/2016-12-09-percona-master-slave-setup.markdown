---
layout: post
title: MySQL主从架构搭建 
date: 2016-12-09 19:22:31 +0800
category: 技术
tags:   mysql   
keywords: mysql masterslave
description: 
---
1. 安装MySQL服务器    
分别安装MySQL服务器（从库需要对主库版本兼容）   
```
master: (100.4.230.14, 3306)
slave : (100.5.233.200, 3306)
```

2. 创建复制账号（master 上）    
```
grant replication slave on *.* to 'slave'@'%' identified by '1234';
```

3. 验证复制账号（slave 上）    
```
mysql -uslave -p1234 -h100.4.230.14 -P 3306;
```

4. 配置部署        
```
\#\#修改master配置(my.cnf)
\#设置服务器ID
[mysqld]
server-id=1
\#开启binlog
log-bin=mysql-bin
\#设置binlog格式   
binlog-format=row
\#5.6版本开启GTID  
gtid_mode=ON
enforce-gtid-consistency=ON

\#\#修改slave配置(my.cnf)  
[mysqld]
\#这只服务器ID，与master不应该一致   
server-id=2
\#开启binlog
log-bin=mysql-bin
\#设置binlog格式   
binlog-format=row
\#5.6版本开启GTID
gtid_mode=ON
enforce-gtid-consistency=ON
```

5. 查看master状态   
```
show master status;#5.6多了gtid
```

6. 搭建复制关系（slave 上）  
```
\#5.5
change master to master_host='100.4.230.14', master_port=3306, master_user='slave', master_password='1234', MASTER_LOG_FILE='mysql-bin.000001'
\#5.6
change master to master_host='100.4.230.14', master_port3306, master_user='slave', master_password='1234', MASTER_AUTO_POSITION=1, MASTER_HEARTBEAT_PERIOD=60;
```

7. 启动复制线程（slave上）   
```
start slave;
```

8. 查看复制状态（slave上）   
```
show slave status\G
```

9. 状态判断    
只有下述两项均为ON时，才会同步:     
```
Slave_IO_Running: YES/NO
Slave_SQL_Running: YES/NO
```

