# linux ���������ű�

����������ļ���

```
vi /etc/rc.d/init.d/restart_Harbor
```

�ļ�������������ݣ�

```shell
#!/bin/sh
#chkconfig: 2345 80 90
#description: auto_run
cd /usr/local/docker/harbor/
touch /usr/local/docker/harbor/imhere
docker-compose down
docker-compose up -d
```

�����˳��������������Ȩ�ޣ�

```shell
chmod +x restart_Harbor
```

����ִ�������������

```shell
chkconfig --add restart_Harbor
chkconfig restart_Harbor on
```

�󹦸�ɣ��������ִ�� restart_Harbor �ű�

