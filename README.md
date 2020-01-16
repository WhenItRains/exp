[top]
# 图片下载
## java 后端代码:

    @RestController
    public class ImgViewController {

        @RequestMapping(value = "/imgShow")
        public void imgShow(String imgPath, HttpServletResponse response) {
            FileInputStream fis = null;
            response.setContentType("image/gif");
            try {
                OutputStream out = response.getOutputStream();
                File file = new File("G:" + File.separator + imgPath);
                fis = new FileInputStream(file);
                byte[] b = new byte[fis.available()];
                fis.read(b);
                out.write(b);
                out.flush();
            } catch (Exception e) {
                e.printStackTrace();
            } finally {
                if (fis != null) {
                    try {
                        fis.close();
                    } catch (IOException e) {
                        e.printStackTrace();
                    }
                }
            }

        }
    }
## 前端代码:
#### 第一种方式：
    <img src="http://localhost:8080/imgShow?imgurl"> 
    直接将图片的请求放入src
    优点:简单，方便 请求可以是get请求，可以获取不同图片
    缺点:只能是get请求
 #### 第二种方式：   
    //通过请求后response
    let blob = new Blob([res.data]);
    let imgUrl = window.URL.createObjectURL(blob);
    将imgUrl 赋值到<img src="imgUrl">

# Linux和docker 命令
#### 进入docker 某项目中
> docker exec -it 10e723ab7004 /bin/bash

#### 进入docker后退出
> Exit

#### docker安装vim 和yum 命令
> apt-get update
apt-get install yum -y
apt-get install vim -y

#### XShell上传文件到Linux服务器上
> 输入rz命令，看是否已经安装了lrzsz，如果没有安装则执行yum -y install lrzsz命令进行安装。
验证安装成功：rpm -qa lrzsz
使用 rz -y命令进行文件上传

#### rz、sz命令找不到：
> 执行命令：apt-get update && apt-get install lrzsz

#### 删除容器
> docker rm -f ed8(容器ID)

#### 查看linux版本
> rpm -q centos-release

#### 查询是否有vim
> rpm -qa|grep vim

#### 安装vim
> yum -y install vim*

#### 更新profile配置
> source /etc/profile

--------------------




# Linux设置tomcat开机自启动
	前提是你已经安装好了tomcat服务。
	配置Tomcat开机启动很简单，将Tomcat配置为系统服务并配置为开机启动即可。

#### (一) 将tomcat配置为系统服务：创建tomcat8服务文件
> vi /usr/lib/systemd/system/tomcat8.service。

#### (二) tomcat8.service 文件内容：

	[Unit]
	Description=Tomcat8
	After=syslog.target network.target remote-fs.target nss-lookup.target
	[Service]
	Type=forking
	Environment='JAVA_HOME=/data/server/jdk-1.8'
	Environment='CATALINA_PID=/data/server/tomcat8/bin/tomcat.pid'
	Environment='CATALINA_HOME=/data/server/tomcat8/'
	Environment='CATALINA_BASE=/data/server/tomcat8/'
	Environment='CATALINA_OPTS=-Xms512M -Xmx1024M -server -XX:+UseParallelGC'
	WorkingDirectory=/data/server/tomcat8/
	ExecStart=/data/server/tomcat8/bin/startup.sh
	ExecReload=/bin/kill -s HUP $MAINPID
	ExecStop=/bin/kill -s QUIT $MAINPID
	PrivateTmp=true
	[Install]
	WantedBy=multi-user.target

#### (三) 接下来配置tomcat开机启动：
> 设置tomcat开机启动：systemctl enable tomcat8
启动tomcat8服务：systemctl start tomcat8

#### (四) 现在就让我们重启一下，然后查看一下服务里面有没有，就知道成不成功了。
> 重启：reboot


#### (五) 如果查找到有2个的话就是成功了Linux设置tomcat开机自启动：
> 查看服务中有没有tomcat：ps aux | grep tomcat |wc -l


#### (六）其他用到命令和知识
##### 移除开机项
> systemctl disable zabbix-server.service


##### Systemd的启动顺序
> /etc/systemd/system/
/run/systemd/system/
/usr/lib/systemd/system/


------------
# Tomcat和JDK安装
#### 环境描述：
> centos7最小安装，配置tomcat8

#### 1.可用本地电脑下载jdk1.81.可用本地电脑下载jdk1.8
> 官网如下，或需要注册Oracle账号登录后才可下载
https://www.oracle.com/technetwork/java/javase/downloads/index.html

![](https://www.showdoc.cc/server/api/common/visitfile/sign/ee8357b08a503dcfabf2eab58fe60d83?showdoc=.jpg)

#### 2.安装上传工具2.安装上传工具
	[root@localhost ~]# yum -y install lrzsz
	上传jdk
	[root@localhost ~]# rz
![](https://www.showdoc.cc/server/api/common/visitfile/sign/e15958ad2cceea7526856b660d2df293?showdoc=.jpg)
#### 3.jdk上传OK后解压
	[root@localhost ~]# ls
	anaconda-ks.cfg  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# tar xf jdk-8u201-linux-i586.tar.gz 
	[root@localhost ~]# ls
	anaconda-ks.cfg  jdk1.8.0_201  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# mkdir -p /usr/local/
	bin/     etc/     games/   include/ lib/     lib64/   libexec/ sbin/    share/   src/     
	[root@localhost ~]# mkdir /usr/local/java
	[root@localhost ~]# mv jdk1.8.0_201/* /usr/local/java/
#### 4.jdk环境变量配置
[root@localhost ~]# vim /etc/profile #追加如下变量

	export JAVA_HOME=/usr/local/java/jdk1.8.0_201
	export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
	export PATH=$PATH:$JAVA_HOME/bin
#### 5.更新profile文件
	[root@localhost ~]# source /etc/profile
#### 6.查看java版本
	[root@localhost local]# java -version
	-bash: /usr/local/java/bin/java: /lib/ld-linux.so.2: bad ELF interpreter: 没有那个文件或目录
**出错了：提示没有文件。
此情况应该是最小安装系统缺少相应的库文件导致出错
这里可根据提示安装相应的库文件即可**

	[root@localhost ~]# yum -y install ld-linux.so.2
	[root@localhost ~]# java -version
	java version "1.8.0_201"
	Java(TM) SE Runtime Environment (build 1.8.0_201-b09)
	Java HotSpot(TM) Client VM (build 25.201-b09, mixed mode)
	[root@localhost ~]# javac -version
	javac 1.8.0_201

**安装完提示缺少的文件后，再次查看Java版本，OK。**
#### 7.下载tomcat8
> 官网地址 https://tomcat.apache.org/download-80.cgi
依然下载到本地后再rz上传

![](https://www.showdoc.cc/server/api/common/visitfile/sign/3552885a178e99999a84532e6d99b860?showdoc=.jpg)
#### 8.上传tomcat8并解压

![](https://www.showdoc.cc/server/api/common/visitfile/sign/98b45c8e047c20f8047a9e8d08583640?showdoc=.jpg)

	[root@localhost ~]# rz
	[root@localhost ~]# ls
	anaconda-ks.cfg  apache-tomcat-8.5.41.tar.gz  jdk1.8.0_201  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# tar xf apache-tomcat-8.5.41.tar.gz 
	[root@localhost ~]# ls
	anaconda-ks.cfg  apache-tomcat-8.5.41  apache-tomcat-8.5.41.tar.gz  jdk1.8.0_201  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# mkdir /usr/local/tomcat8
	[root@localhost ~]# mv apache-tomcat-8.5.41/* /usr/local/tomcat8/

#### 9.启动tomcat
	[root@localhost ~]# /usr/local/tomcat8/bin/startup.sh 
	Using CATALINA_BASE:   /usr/local/tomcat8
	Using CATALINA_HOME:   /usr/local/tomcat8
	Using CATALINA_TMPDIR: /usr/local/tomcat8/temp
	Using JRE_HOME:        /usr/local/java
	Using CLASSPATH:       /usr/local/tomcat8/bin/bootstrap.jar:/usr/local/tomcat8/bin/tomcat-juli.jar
	Tomcat started.
	[root@localhost ~]# ps -ef|grep java
	root       9744      1 31 16:44 pts/0    00:00:03 /usr/local/java/bin/java -Djava.util.logging.config.file=/usr/local/tomcat8/conf/logging.properties -Djava.util.logging.manager=org.apache.juli.ClassLoaderLogManager -Djdk.tls.ephemeralDHKeySize=2048 -Djava.protocol.handler.pkgs=org.apache.catalina.webresources -Dorg.apache.catalina.security.SecurityListener.UMASK=0027 -Dignore.endorsed.dirs= -classpath /usr/local/tomcat8/bin/bootstrap.jar:/usr/local/tomcat8/bin/tomcat-juli.jar -Dcatalina.base=/usr/local/tomcat8 -Dcatalina.home=/usr/local/tomcat8 -Djava.io.tmpdir=/usr/local/tomcat8/temp org.apache.catalina.startup.Bootstrap start root       9787   7172  0 16:44 pts/0    00:00:00 grep --color=auto java

**启动完成，查看进程OK。**
#### 10.页面验证
http://.......:8080/

![](https://www.showdoc.cc/server/api/common/visitfile/sign/ae516d016ec1d3e404236a55583d269e?showdoc=.jpg)

#### 此为防火墙在开启状态，访问被阻，关闭防火墙或者允许页面端口通过都可以。
实验环境可关闭防火墙：
	[root@localhost ~]# systemctl stop firewalld
	[root@localhost ~]# systemctl disable firewalld
	Removed symlink /etc/systemd/system/multi-user.target.wants/firewalld.service.
	Removed symlink /etc/systemd/system/dbus-org.fedoraproject.FirewallD1.service.
#### 生产环境建议开启端口即可，增强服务器安全性：
	[root@localhost tomcat8]# firewall-cmd --permanent --add-port=8080/tcp
	success
	[root@localhost tomcat8]# firewall-cmd --reload
	success
	
![](https://www.showdoc.cc/server/api/common/visitfile/sign/607a310c4cc93f054d415ac5f4fe2abc?showdoc=.jpg)
## 久违的tomcat页面显示OK

------------
# 部署遇到问题
> 部署docker时，遇到tomcat无法访问mysql。由于有内外端口映射，而且 tomcat与mysql在同一容器，所以将后端项目连接mysql端口不用更改为外端口，Redis同理，其他数据库，中间件同理！



