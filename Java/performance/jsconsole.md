-Djava.rmi.server.hostname=11.11.15.20 -Dcom.sun.management.jmxremote -Dcom.sun.management.jmxremote.port=9111 -Dcom.sun.management.jmxremote.ssl=false -Dcom.sun.management.jmxremote.authenticate=false





```
[root@localhost bin]# cd /usr/lib/jvm/java-1.8.0-openjdk-1.8.0.101-3.b13.el7_2.x86_64/jre/lib/management/

[root@localhost management]# cp jmxremote.password.template jmxremote.password

[root@localhost management]# vi jmxremote.password
```

monitorRole QED
controlRole sysadm

3.配置权限文件为600

```
`[root@localhost management]``# chmod 600 jmxremote.password jmxremote.access`
```

　　

这样基本配置就结束了，下面说两个坑，第一个就是防火墙的问题，要开放指定端口的防火墙，我这里配置的是12345端口，第二个是hostname的问题

```
`[root@localhost lib]``# vi /etc/hosts`
```

![img](https://images2015.cnblogs.com/blog/656873/201612/656873-20161206173351382-2060740719.png)

请将127.0.0.1修改为本地真实的IP,我的服务器IP是11.11.15.20 (也可以不改，也能顺利执行)

![img](https://images2015.cnblogs.com/blog/656873/201612/656873-20161206173450866-1037716294.png)

 远程进程：

11.11.15.20:9111

用户名：sysadm 口令：Pos3c0xe@t5c4jl_20



![1571304979102](C:\Users\admin\AppData\Roaming\Typora\typora-user-images\1571304979102.png)