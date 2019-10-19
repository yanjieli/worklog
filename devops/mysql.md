# mysql install

systemctl stop firewalld

systemctl disabled firewalld

yum remove mysql-libs mariadb-libs

rpm -ivh mysql-community-common-5.7.19-1.el7.x86_64.rpm

rpm -ivh mysql-community-libs-5.7.19-1.el7.x86_64.rpm

rpm -ivh mysql-community-client-5.7.19-1.el7.x86_64.rpm

rpm -ivh mysql-community-server-5.7.19-1.el7.x86_64.rpm

rpm -ivh mysql-community-devel-5.7.19-1.el7.x86_64.rpm （可选）

systemctl restart mysqld

systemctl status mysqld

cat /var/log/mysqld.log | grep password  

alter user 'root'@'localhost' identified by 'Welcome_1';  



# docker install

yum install docker

#docker version

[root@localhost docker]# docker version
Client:
 Version:         1.13.1
 API version:     1.26
 Package version: docker-1.13.1-103.git7f2769b.el7.centos.x86_64
 Go version:      go1.10.3
 Git commit:      7f2769b/1.13.1
 Built:           Sun Sep 15 14:06:47 2019
 OS/Arch:         linux/amd64

Server:
 Version:         1.13.1
 API version:     1.26 (minimum version 1.12)
 Package version: docker-1.13.1-103.git7f2769b.el7.centos.x86_64
 Go version:      go1.10.3
 Git commit:      7f2769b/1.13.1
 Built:           Sun Sep 15 14:06:47 2019
 OS/Arch:         linux/amd64
 Experimental:    false





