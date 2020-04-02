<!-- TOC -->

- [工作问题总结](#%e5%b7%a5%e4%bd%9c%e9%97%ae%e9%a2%98%e6%80%bb%e7%bb%93)
  - [守护线程问题 (setDaemon)](#%e5%ae%88%e6%8a%a4%e7%ba%bf%e7%a8%8b%e9%97%ae%e9%a2%98-setdaemon)
- [图片下载](#%e5%9b%be%e7%89%87%e4%b8%8b%e8%bd%bd)
  - [java 后端代码:](#java-%e5%90%8e%e7%ab%af%e4%bb%a3%e7%a0%81)
  - [前端代码:](#%e5%89%8d%e7%ab%af%e4%bb%a3%e7%a0%81)
    - [第一种方式：](#%e7%ac%ac%e4%b8%80%e7%a7%8d%e6%96%b9%e5%bc%8f)
    - [第二种方式：](#%e7%ac%ac%e4%ba%8c%e7%a7%8d%e6%96%b9%e5%bc%8f)
- [Linux和docker 命令](#linux%e5%92%8cdocker-%e5%91%bd%e4%bb%a4)
  - [进入docker 某项目中](#%e8%bf%9b%e5%85%a5docker-%e6%9f%90%e9%a1%b9%e7%9b%ae%e4%b8%ad)
  - [进入docker后退出](#%e8%bf%9b%e5%85%a5docker%e5%90%8e%e9%80%80%e5%87%ba)
  - [docker安装vim 和yum 命令](#docker%e5%ae%89%e8%a3%85vim-%e5%92%8cyum-%e5%91%bd%e4%bb%a4)
  - [XShell上传文件到Linux服务器上](#xshell%e4%b8%8a%e4%bc%a0%e6%96%87%e4%bb%b6%e5%88%b0linux%e6%9c%8d%e5%8a%a1%e5%99%a8%e4%b8%8a)
  - [rz、sz命令找不到：](#rzsz%e5%91%bd%e4%bb%a4%e6%89%be%e4%b8%8d%e5%88%b0)
  - [删除容器](#%e5%88%a0%e9%99%a4%e5%ae%b9%e5%99%a8)
  - [查看linux版本](#%e6%9f%a5%e7%9c%8blinux%e7%89%88%e6%9c%ac)
  - [安装tar命令](#%e5%ae%89%e8%a3%85tar%e5%91%bd%e4%bb%a4)
  - [查询是否有vim](#%e6%9f%a5%e8%af%a2%e6%98%af%e5%90%a6%e6%9c%89vim)
  - [安装vim](#%e5%ae%89%e8%a3%85vim)
  - [更新profile配置](#%e6%9b%b4%e6%96%b0profile%e9%85%8d%e7%bd%ae)
- [Linux设置tomcat开机自启动](#linux%e8%ae%be%e7%bd%aetomcat%e5%bc%80%e6%9c%ba%e8%87%aa%e5%90%af%e5%8a%a8)
  - [(一) 将tomcat配置为系统服务：创建tomcat8服务文件](#%e4%b8%80-%e5%b0%86tomcat%e9%85%8d%e7%bd%ae%e4%b8%ba%e7%b3%bb%e7%bb%9f%e6%9c%8d%e5%8a%a1%e5%88%9b%e5%bb%batomcat8%e6%9c%8d%e5%8a%a1%e6%96%87%e4%bb%b6)
  - [(二) tomcat8.service 文件内容：](#%e4%ba%8c-tomcat8service-%e6%96%87%e4%bb%b6%e5%86%85%e5%ae%b9)
  - [(三) 接下来配置tomcat开机启动：](#%e4%b8%89-%e6%8e%a5%e4%b8%8b%e6%9d%a5%e9%85%8d%e7%bd%aetomcat%e5%bc%80%e6%9c%ba%e5%90%af%e5%8a%a8)
  - [(四) 现在就让我们重启一下，然后查看一下服务里面有没有，就知道成不成功了。](#%e5%9b%9b-%e7%8e%b0%e5%9c%a8%e5%b0%b1%e8%ae%a9%e6%88%91%e4%bb%ac%e9%87%8d%e5%90%af%e4%b8%80%e4%b8%8b%e7%84%b6%e5%90%8e%e6%9f%a5%e7%9c%8b%e4%b8%80%e4%b8%8b%e6%9c%8d%e5%8a%a1%e9%87%8c%e9%9d%a2%e6%9c%89%e6%b2%a1%e6%9c%89%e5%b0%b1%e7%9f%a5%e9%81%93%e6%88%90%e4%b8%8d%e6%88%90%e5%8a%9f%e4%ba%86)
  - [(五) 如果查找到有2个的话就是成功了Linux设置tomcat开机自启动：](#%e4%ba%94-%e5%a6%82%e6%9e%9c%e6%9f%a5%e6%89%be%e5%88%b0%e6%9c%892%e4%b8%aa%e7%9a%84%e8%af%9d%e5%b0%b1%e6%98%af%e6%88%90%e5%8a%9f%e4%ba%86linux%e8%ae%be%e7%bd%aetomcat%e5%bc%80%e6%9c%ba%e8%87%aa%e5%90%af%e5%8a%a8)
  - [(六）其他用到命令和知识](#%e5%85%ad%e5%85%b6%e4%bb%96%e7%94%a8%e5%88%b0%e5%91%bd%e4%bb%a4%e5%92%8c%e7%9f%a5%e8%af%86)
    - [移除开机项](#%e7%a7%bb%e9%99%a4%e5%bc%80%e6%9c%ba%e9%a1%b9)
    - [Systemd的启动顺序](#systemd%e7%9a%84%e5%90%af%e5%8a%a8%e9%a1%ba%e5%ba%8f)
- [Tomcat和JDK安装](#tomcat%e5%92%8cjdk%e5%ae%89%e8%a3%85)
  - [环境描述：](#%e7%8e%af%e5%a2%83%e6%8f%8f%e8%bf%b0)
  - [可用本地电脑下载jdk1.81.可用本地电脑下载jdk1.8](#%e5%8f%af%e7%94%a8%e6%9c%ac%e5%9c%b0%e7%94%b5%e8%84%91%e4%b8%8b%e8%bd%bdjdk181%e5%8f%af%e7%94%a8%e6%9c%ac%e5%9c%b0%e7%94%b5%e8%84%91%e4%b8%8b%e8%bd%bdjdk18)
  - [安装上传工具2.安装上传工具](#%e5%ae%89%e8%a3%85%e4%b8%8a%e4%bc%a0%e5%b7%a5%e5%85%b72%e5%ae%89%e8%a3%85%e4%b8%8a%e4%bc%a0%e5%b7%a5%e5%85%b7)
  - [jdk上传OK后解压](#jdk%e4%b8%8a%e4%bc%a0ok%e5%90%8e%e8%a7%a3%e5%8e%8b)
  - [jdk环境变量配置](#jdk%e7%8e%af%e5%a2%83%e5%8f%98%e9%87%8f%e9%85%8d%e7%bd%ae)
  - [更新profile文件](#%e6%9b%b4%e6%96%b0profile%e6%96%87%e4%bb%b6)
  - [查看java版本](#%e6%9f%a5%e7%9c%8bjava%e7%89%88%e6%9c%ac)
  - [下载tomcat8](#%e4%b8%8b%e8%bd%bdtomcat8)
  - [上传tomcat8并解压](#%e4%b8%8a%e4%bc%a0tomcat8%e5%b9%b6%e8%a7%a3%e5%8e%8b)
    - [启动tomcat](#%e5%90%af%e5%8a%a8tomcat)
  - [页面验证](#%e9%a1%b5%e9%9d%a2%e9%aa%8c%e8%af%81)
  - [此为防火墙在开启状态，访问被阻，关闭防火墙或者允许页面端口通过都可以。](#%e6%ad%a4%e4%b8%ba%e9%98%b2%e7%81%ab%e5%a2%99%e5%9c%a8%e5%bc%80%e5%90%af%e7%8a%b6%e6%80%81%e8%ae%bf%e9%97%ae%e8%a2%ab%e9%98%bb%e5%85%b3%e9%97%ad%e9%98%b2%e7%81%ab%e5%a2%99%e6%88%96%e8%80%85%e5%85%81%e8%ae%b8%e9%a1%b5%e9%9d%a2%e7%ab%af%e5%8f%a3%e9%80%9a%e8%bf%87%e9%83%bd%e5%8f%af%e4%bb%a5)
  - [生产环境建议开启端口即可，增强服务器安全性：](#%e7%94%9f%e4%ba%a7%e7%8e%af%e5%a2%83%e5%bb%ba%e8%ae%ae%e5%bc%80%e5%90%af%e7%ab%af%e5%8f%a3%e5%8d%b3%e5%8f%af%e5%a2%9e%e5%bc%ba%e6%9c%8d%e5%8a%a1%e5%99%a8%e5%ae%89%e5%85%a8%e6%80%a7)
  - [久违的tomcat页面显示OK](#%e4%b9%85%e8%bf%9d%e7%9a%84tomcat%e9%a1%b5%e9%9d%a2%e6%98%be%e7%a4%baok)
  - [部署遇到问题](#%e9%83%a8%e7%bd%b2%e9%81%87%e5%88%b0%e9%97%ae%e9%a2%98)

<!-- /TOC -->

# 工作问题总结

## 守护线程问题 (setDaemon)
  **介绍**:守护线程：在操作系统里面是没有所谓的守护线程的概念的，只有守护进程一说。但是Java语言机制是构建在JVM的基础之上的，这一机制意味着Java平台是把操作系统的底层给屏蔽了起来，所以它可以在它自己的虚拟的平台里面构造出对自己有利的机制。而Java语言或者说平台的设计者多多少少是收到Unix操作系统思想的影响，而守护线程机制又是对JVM这样的平台凑合，于是守护线程应运而生。

所谓的守护线程，指的是程序运行时在后台提供的一种通用服务的线程。比如垃圾回收线程就是一个很称职的守护者，并且这种线程并不属于程序中不可或缺的部分。因此，当所有的非守护线程结束时，程序也就终止了，同时会杀死进程中的所有守护线程。反过来说，只要任何非守护线程还在运行，程序就不会终止。

事实上，User Thread（用户线程）和Daemon Thread（守护线程）从本质上来说并没有什么区别，唯一的不同之处就在于虚拟机的离开：如果用户线程已经全部退出运行了，只剩下守护线程存在了，虚拟机也就退出了。 因为没有了被守护者，守护线程也就没有工作可做了，也就没有继续运行程序的必要了。

**简单理解**:

    主线程
        main，但不是守护线程。
    守护线程
        是指在程序运行的时候在后台提供一种通用服务的线程。如gc。
    非守护线程
        也叫用户线程，由用户创建。
    关系：
        主线程和守护线程一起销毁；
        主线程和非守护线程互不影响。
**问题介绍**: tomcat在调用 ./shutdown后,使用 ps -ef|grep tomcat 命令项目还在运行！

**解决过程**:

1. [解决linux下tomcat停止进程任存在问题]https://www.jianshu.com/p/ab14b7718016
2. 根据查找办法，*将自己使用的线程池设置为守护线程*，并且，*在项目停止的回调方法中,释放线程资源*
**代码补充**:
1. 自己使用的线程池设置为守护线程
```java
 @Bean
public ExecutorService threadPool(){
    ThreadFactory namedThreadFactory = new ThreadFactoryBuilder()
            .setNameFormat("    kafkaThredadPool-%d").setDaemon(true).build();
    ExecutorService singleThreadPool = new ThreadPoolExecutor(4, 6,
            0L, TimeUnit.MILLISECONDS,
            new LinkedBlockingQueue<Runnable>(1024), namedThreadFactory, new ThreadPoolExecutor.AbortPolicy());
    return singleThreadPool;
}
```
2. 在项目停止的回调方法中,释放线程资源
```java
@Component
public class EndGlobalKeyboard {
    private static Logger logger = LoggerFactory.getLogger(EndGlobalKeyboard.class);
    @Resource
    private ExecutorService threadPool;
    @PreDestroy
    public void destory() throws Exception {
        logger.info("destory 关闭" + threadPool.isShutdown());
        threadPool.shutdown();
    }
}
```

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
    	
	如果文件很大，在springboot配置文件中，更改文件大小
	文件上传大小为20M 
	spring.servlet.multipart.max-file-size=20MB
	请求大小为20M
	pring.servlet.multipart.max-request-size=20MB

## 前端代码:

### 第一种方式：
    <img src="http://localhost:8080/imgShow?imgurl"> 
    直接将图片的请求放入src
    优点:简单，方便 请求可以是get请求，可以获取不同图片
    缺点:只能是get请求

### 第二种方式：   
    //通过请求后response
    let blob = new Blob([res.data]);
    let imgUrl = window.URL.createObjectURL(blob);
    将imgUrl 赋值到<img src="imgUrl">

# Linux和docker 命令

## 进入docker 某项目中
> docker exec -it 10e723ab7004 /bin/bash

## 进入docker后退出
> Exit

## docker安装vim 和yum 命令
> apt-get update
apt-get install yum -y
apt-get install vim -y

## XShell上传文件到Linux服务器上
> 输入rz命令，看是否已经安装了lrzsz，如果没有安装则执行yum -y install lrzsz命令进行安装。
验证安装成功：rpm -qa lrzsz
使用 rz -y命令进行文件上传

## rz、sz命令找不到：
> 执行命令：apt-get update && apt-get install lrzsz

## 删除容器
> docker rm -f ed8(容器ID)

## 查看linux版本
> rpm -q centos-release

## 安装tar命令
> yum install -y tar

## 查询是否有vim
> rpm -qa|grep vim

## 安装vim
> yum -y install vim*

## 更新profile配置
> source /etc/profile

--------------------




# Linux设置tomcat开机自启动
	前提是你已经安装好了tomcat服务。
	配置Tomcat开机启动很简单，将Tomcat配置为系统服务并配置为开机启动即可。

## (一) 将tomcat配置为系统服务：创建tomcat8服务文件
> vi /usr/lib/systemd/system/tomcat8.service。

## (二) tomcat8.service 文件内容：

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

## (三) 接下来配置tomcat开机启动：
> 设置tomcat开机启动：systemctl enable tomcat8
启动tomcat8服务：systemctl start tomcat8

## (四) 现在就让我们重启一下，然后查看一下服务里面有没有，就知道成不成功了。
> 重启：reboot


## (五) 如果查找到有2个的话就是成功了Linux设置tomcat开机自启动：
> 查看服务中有没有tomcat：ps aux | grep tomcat |wc -l


## (六）其他用到命令和知识

### 移除开机项
> systemctl disable zabbix-server.service


### Systemd的启动顺序
> /etc/systemd/system/
/run/systemd/system/
/usr/lib/systemd/system/


------------

# Tomcat和JDK安装

## 环境描述：
> centos7最小安装，配置tomcat8

## 可用本地电脑下载jdk1.81.可用本地电脑下载jdk1.8
> 官网如下，或需要注册Oracle账号登录后才可下载
https://www.oracle.com/technetwork/java/javase/downloads/index.html

![](https://www.showdoc.cc/server/api/common/visitfile/sign/ee8357b08a503dcfabf2eab58fe60d83?showdoc=.jpg)

## 安装上传工具2.安装上传工具
	[root@localhost ~]# yum -y install lrzsz
	上传jdk
	[root@localhost ~]# rz
![](https://www.showdoc.cc/server/api/common/visitfile/sign/e15958ad2cceea7526856b660d2df293?showdoc=.jpg)

## jdk上传OK后解压
	[root@localhost ~]# ls
	anaconda-ks.cfg  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# tar xf jdk-8u201-linux-i586.tar.gz 
	[root@localhost ~]# ls
	anaconda-ks.cfg  jdk1.8.0_201  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# mkdir -p /usr/local/
	bin/     etc/     games/   include/ lib/     lib64/   libexec/ sbin/    share/   src/     
	[root@localhost ~]# mkdir /usr/local/java
	[root@localhost ~]# mv jdk1.8.0_201/* /usr/local/java/

## jdk环境变量配置
[root@localhost ~]# vim /etc/profile #追加如下变量

	export JAVA_HOME=/usr/local/java/jdk1.8.0_201
	export CLASSPATH=.:$JAVA_HOME/lib/dt.jar:$JAVA_HOME/lib/tools.jar
	export PATH=$PATH:$JAVA_HOME/bin

## 更新profile文件
	[root@localhost ~]# source /etc/profile

## 查看java版本
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

## 下载tomcat8
> 官网地址 https://tomcat.apache.org/download-80.cgi
依然下载到本地后再rz上传

![](https://www.showdoc.cc/server/api/common/visitfile/sign/3552885a178e99999a84532e6d99b860?showdoc=.jpg)

## 上传tomcat8并解压

![](https://www.showdoc.cc/server/api/common/visitfile/sign/98b45c8e047c20f8047a9e8d08583640?showdoc=.jpg)

	[root@localhost ~]# rz
	[root@localhost ~]# ls
	anaconda-ks.cfg  apache-tomcat-8.5.41.tar.gz  jdk1.8.0_201  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# tar xf apache-tomcat-8.5.41.tar.gz 
	[root@localhost ~]# ls
	anaconda-ks.cfg  apache-tomcat-8.5.41  apache-tomcat-8.5.41.tar.gz  jdk1.8.0_201  jdk-8u201-linux-i586.tar.gz
	[root@localhost ~]# mkdir /usr/local/tomcat8
	[root@localhost ~]# mv apache-tomcat-8.5.41/* /usr/local/tomcat8/

### 启动tomcat
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

## 页面验证
http://.......:8080/

![](https://www.showdoc.cc/server/api/common/visitfile/sign/ae516d016ec1d3e404236a55583d269e?showdoc=.jpg)

## 此为防火墙在开启状态，访问被阻，关闭防火墙或者允许页面端口通过都可以。
实验环境可关闭防火墙：
	[root@localhost ~]# systemctl stop firewalld
	[root@localhost ~]# systemctl disable firewalld
	Removed symlink /etc/systemd/system/multi-user.target.wants/firewalld.service.
	Removed symlink /etc/systemd/system/dbus-org.fedoraproject.FirewallD1.service.

## 生产环境建议开启端口即可，增强服务器安全性：
	[root@localhost tomcat8]# firewall-cmd --permanent --add-port=8080/tcp
	success
	[root@localhost tomcat8]# firewall-cmd --reload
	success
	
![](https://www.showdoc.cc/server/api/common/visitfile/sign/607a310c4cc93f054d415ac5f4fe2abc?showdoc=.jpg)

## 久违的tomcat页面显示OK

------------

## 部署遇到问题
> 部署docker时，遇到tomcat无法访问mysql。由于有内外端口映射，而且 tomcat与mysql在同一容器，所以将后端项目连接mysql端口不用更改为外端口，Redis同理，其他数据库，中间件同理！
