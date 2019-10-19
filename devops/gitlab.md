# centos安装gitlab

2019.07.13 08:55:47字数 219阅读 203

# centos安装gitlab

### 一、安装并配置必要的依赖关系

#### 1.安装ssh

sudo yum install -y curl policycoreutils-python openssh-server

#### 2、启动ssh并设置为开机自启动

sudo systemctl enable sshd

systemctl start sshd

#### 3、添加http服务到firewalld,pemmanent表示永久生效，若不加--permanent系统下次启动后就会失效

systemctl start firewalld

firewall-cmd --permanent --add-service=http

systemctl reload firewalld

#### 4、启动postfix

systemctl enable postfix

systemctl start postfix

#### 5、下载gitlab安装文件

wget [https://mirrors.tuna.tsinghua.edu.cn/gitlab-ce/yum/el7/gitlab-ce-10.0.0-ce.0.el7.x86_64.rpm](https://links.jianshu.com/go?to=https%3A%2F%2Fmirrors.tuna.tsinghua.edu.cn%2Fgitlab-ce%2Fyum%2Fel7%2Fgitlab-ce-10.0.0-ce.0.el7.x86_64.rpm)

#### 6、执行安装

rpm -i gitlab-ce-10.0.0-ce.0.el7.x86_64.rpm



![img](https://upload-images.jianshu.io/upload_images/14297483-409cb73c75083c6f.png?imageMogr2/auto-orient/strip|imageView2/2/w/727/format/webp)

image.png

#### 7、编辑ip和端口

vim /etc/gitlab/gitlab.rb



![img](https://upload-images.jianshu.io/upload_images/14297483-f242618af78662cd.png?imageMogr2/auto-orient/strip|imageView2/2/w/591/format/webp)

image.png



gitlab-ctl reconfigure

gitlab-ctl restart

### 8、访问gitlab

如果输入端口和ip一直无法响应，可以关闭防火墙

systemctl stop firewalld

重新配置并启动

gitlab-ctl reconfigure

gitlab-ctl restart