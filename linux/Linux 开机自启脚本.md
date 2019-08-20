# linux 开机自启脚本

输入命令创建文件：

```
vi /etc/rc.d/init.d/restart_Harbor
```

文件中添加如下内容：

```shell
#!/bin/sh
#chkconfig: 2345 80 90
#description: auto_run
cd /usr/local/docker/harbor/
touch /usr/local/docker/harbor/imhere
docker-compose down
docker-compose up -d
```

保存退出，输入命令添加权限：

```shell
chmod +x restart_Harbor
```

依次执行以下两条命令：

```shell
chkconfig --add restart_Harbor
chkconfig restart_Harbor on
```

大功告成，开机便会执行 restart_Harbor 脚本

