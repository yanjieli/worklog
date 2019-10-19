### 什么是大数据，核心问题

1.举例：

2.核心问题：

数据的存储：分布式文件系统

数据的计算：分布式计算，离线计算，实时计算（流式计算）

spark core flink dataset mapreduce 离线计算

storm sparkstreaming flink datastream 实时计算

### 什么是数据仓库

本质就是一个数据库 

oracle dbca

一般数据仓库只做查询操作。

搭建数据仓库过程：RDBMS，文本，其他数据源。ETL（Extract transform load）抽取清洗转换存储到数据仓库

数据集市：oracle，mysql等面向主题的数据库

BDP京东的大数据平台。70个数据集市，60个给京东商城。10个给物流等。

除传统的oracle外，Hadoop，spark，flink都可以是数据仓库的一种实现方式，大数据实现。

sqoop和flume都可以实现ETL。flume 针对日志等文本。sqoop针对关系型数据库。

Hbase是一个NOsql数据库，根据google的大表提出来，依然存在HDFS中。

Hive基于HDFS的数据仓库查询。将sql翻译成mapreduce或者spark处理的大数据。

### OLTP和OLAP

OLTP，online transaction processing连接事务处理

OLAP, online analytic processing 连接分析处理

数据仓库都是做OLAP。



### google的三驾马车: 重点

###### 1.GFS: 

GOOGLE FILE SYSTEM-->HDFS:hadop distributed File System

分布式文件系统的基本原理，都是来解决数据存储的问题。

解决硬盘不够大和硬盘不够安全的问题。

HDFS默认的数据库冗余度3，可以修改。

第一步，上传数据

第二步，水平复制机架感知的基本原理：安全，效率上考虑。rack rac

fsimage文件存储了数据块的元数据信息

日志文件记录了客户端的操作，edits文件。

secondnamenode负责将edits记录的最新状态信息，写到fsimage文件中去。

###### 2.MapReduce计算模型：问题来源PageRank

为了解决pagerank，提出mapreduce。 网页排名。

核心思想，先拆分再合并。

mapreduce的编程模型。

1.任务job=Map(s)+[reduce（s）]

chainmapper chainreducer

2.Map的输出是reduce的输入

3.所有的输入输出都是key value

4.所有的key value数据类型必须是Hadoop自己的数据类型

Integer->intWritable Long->LongWriteable 

String->text null->NullWriteable 等均实现了hadoop的序列化接口writeable

5.mapreduce的输入输出都是HDFS

​    本地模式的输入输出不是hdfs

6 java编的程序运行在yarn容器中，环境搭建完后就有yarn容器。







###### 3.BigTable 大表：Nosql数据库Hbase

rdbms ，基于二维表的关系模型的数据库，范式,减少数据冗余，降低性能

大表，所有的数据存入一张表，提高性能。

### 搭建hadoop环境

准备工作：关闭防火墙，设置主机名，安装JDK

systemctl stop firewalld;systemctl disable firewalld.

vi /etc/hosts ips hostnames

tar -zxvf jdk.tar.gz. -C '/root/training'

vi .bash_profilejava_home=/root/traning/jdk1.8

export java_home

配置免密登录

ssh-copy-id bigdata130

ssh bigdata130



1.本地模式

特点：没有hdfs和yarn，只能测试mapreduce程序。mapreduce程序只是作为一个普通的java程序来运行。



2.伪分布模式

特点：在单机上模拟一个分布式的环境

HDFS:NameNode,dataNode,SecondaryNameNode

Yarn:ResouceManager NodeManager

hdfs-site.xml

数据块的冗余度，1 到 3.

<peorperty>

​	<name>dfs.replication</name>

​	<value>1</value>

</property>

<peorperty>

​	<name>dfs.permissions   </name>

​	<value>false</value>

</property>

dfs.permissions   禁/用hdfs权限检查

core-site.xml

fs.defaultFS  --hdfs://bigdata130:9000 配置namenode的地址

9000是RPC通信端口

hadoop.tmp.dir --hdfs对应的操作系统目录，默认是/tmp目录，建议必须更改下。防止linux重启丢失数据。

mapred-site.xml

mapreduce.framework.name  yarn --mapreduce运行的框架名称

yarn-site.xml

yarn.resourcemanager.hostname  bigdata130  --yarn的主节点

yarn.nodemanager.aux-services --mapreduce_shuffle  --nodemanager的服务：洗牌



对namenode做格式化，然后才能启动hadoop。

hdfs namenode --format

start -all.sh



3全分布模式：3台

同2，scp -r到从节点上。

4.HA模式 解决主从架构的单点故障问题

借助zookeeper来实现high availability

active/standby namenode resoucemanager

Yarn resource manager-》nodemanager

Hdfs namenode-》datanode

### HDFS

1操作

*命令行

操作命令

管理命令

*java api

*webconsole

50070 namenode

50090 secondarynamenode

2架构组成

###### namenode

###### datamode

apache（4000个节点限制），cdh，HDP 不同版本的搭建。

###### secondarynamenode

secondnamenode负责将edits记录的最新状态信息，写到fsimage文件中去。

start-dfs.sh 

jps show if ready

hdfs dfsadmin -report 查看环境硬件配置信息

hadoop的数据块大小1.x 64M 2.x128M

3.高级特性







#### MapReduce

运行：

hadoop

特性：

(1).序列化，mapreduce的序列化特性，实现了writeable接口

hdfs dfs -ls /input

hdfs dfs -cat /input /data.txt

hadoop jar *.jar wordcount 

（2）排序

（3）分区

(4)