<!-- TOC -->

- [工作问题总结](#%E5%B7%A5%E4%BD%9C%E9%97%AE%E9%A2%98%E6%80%BB%E7%BB%93)
    - [守护线程问题 (setDaemon)](#%E5%AE%88%E6%8A%A4%E7%BA%BF%E7%A8%8B%E9%97%AE%E9%A2%98-setdaemon)
- [图片下载](#%E5%9B%BE%E7%89%87%E4%B8%8B%E8%BD%BD)
    - [java 后端代码:](#java-%E5%90%8E%E7%AB%AF%E4%BB%A3%E7%A0%81)
    - [前端代码:](#%E5%89%8D%E7%AB%AF%E4%BB%A3%E7%A0%81)
        - [第一种方式：](#%E7%AC%AC%E4%B8%80%E7%A7%8D%E6%96%B9%E5%BC%8F)
        - [第二种方式：](#%E7%AC%AC%E4%BA%8C%E7%A7%8D%E6%96%B9%E5%BC%8F)
- [Linux和docker 命令](#linux%E5%92%8Cdocker-%E5%91%BD%E4%BB%A4)
    - [进入docker 某项目中](#%E8%BF%9B%E5%85%A5docker-%E6%9F%90%E9%A1%B9%E7%9B%AE%E4%B8%AD)
    - [进入docker后退出](#%E8%BF%9B%E5%85%A5docker%E5%90%8E%E9%80%80%E5%87%BA)
    - [docker安装vim 和yum 命令](#docker%E5%AE%89%E8%A3%85vim-%E5%92%8Cyum-%E5%91%BD%E4%BB%A4)
    - [XShell上传文件到Linux服务器上](#xshell%E4%B8%8A%E4%BC%A0%E6%96%87%E4%BB%B6%E5%88%B0linux%E6%9C%8D%E5%8A%A1%E5%99%A8%E4%B8%8A)
    - [rz、sz命令找不到：](#rzsz%E5%91%BD%E4%BB%A4%E6%89%BE%E4%B8%8D%E5%88%B0)
    - [删除容器](#%E5%88%A0%E9%99%A4%E5%AE%B9%E5%99%A8)
    - [查看linux版本](#%E6%9F%A5%E7%9C%8Blinux%E7%89%88%E6%9C%AC)
    - [安装tar命令](#%E5%AE%89%E8%A3%85tar%E5%91%BD%E4%BB%A4)
    - [查询是否有vim](#%E6%9F%A5%E8%AF%A2%E6%98%AF%E5%90%A6%E6%9C%89vim)
    - [安装vim](#%E5%AE%89%E8%A3%85vim)
    - [更新profile配置](#%E6%9B%B4%E6%96%B0profile%E9%85%8D%E7%BD%AE)
- [Linux设置tomcat开机自启动](#linux%E8%AE%BE%E7%BD%AEtomcat%E5%BC%80%E6%9C%BA%E8%87%AA%E5%90%AF%E5%8A%A8)
    - [(一) 将tomcat配置为系统服务：创建tomcat8服务文件](#%E4%B8%80-%E5%B0%86tomcat%E9%85%8D%E7%BD%AE%E4%B8%BA%E7%B3%BB%E7%BB%9F%E6%9C%8D%E5%8A%A1%E5%88%9B%E5%BB%BAtomcat8%E6%9C%8D%E5%8A%A1%E6%96%87%E4%BB%B6)
    - [(二) tomcat8.service 文件内容：](#%E4%BA%8C-tomcat8service-%E6%96%87%E4%BB%B6%E5%86%85%E5%AE%B9)
    - [(三) 接下来配置tomcat开机启动：](#%E4%B8%89-%E6%8E%A5%E4%B8%8B%E6%9D%A5%E9%85%8D%E7%BD%AEtomcat%E5%BC%80%E6%9C%BA%E5%90%AF%E5%8A%A8)
    - [(四) 现在就让我们重启一下，然后查看一下服务里面有没有，就知道成不成功了。](#%E5%9B%9B-%E7%8E%B0%E5%9C%A8%E5%B0%B1%E8%AE%A9%E6%88%91%E4%BB%AC%E9%87%8D%E5%90%AF%E4%B8%80%E4%B8%8B%E7%84%B6%E5%90%8E%E6%9F%A5%E7%9C%8B%E4%B8%80%E4%B8%8B%E6%9C%8D%E5%8A%A1%E9%87%8C%E9%9D%A2%E6%9C%89%E6%B2%A1%E6%9C%89%E5%B0%B1%E7%9F%A5%E9%81%93%E6%88%90%E4%B8%8D%E6%88%90%E5%8A%9F%E4%BA%86)
    - [(五) 如果查找到有2个的话就是成功了Linux设置tomcat开机自启动：](#%E4%BA%94-%E5%A6%82%E6%9E%9C%E6%9F%A5%E6%89%BE%E5%88%B0%E6%9C%892%E4%B8%AA%E7%9A%84%E8%AF%9D%E5%B0%B1%E6%98%AF%E6%88%90%E5%8A%9F%E4%BA%86linux%E8%AE%BE%E7%BD%AEtomcat%E5%BC%80%E6%9C%BA%E8%87%AA%E5%90%AF%E5%8A%A8)
    - [(六）其他用到命令和知识](#%E5%85%AD%E5%85%B6%E4%BB%96%E7%94%A8%E5%88%B0%E5%91%BD%E4%BB%A4%E5%92%8C%E7%9F%A5%E8%AF%86)
        - [移除开机项](#%E7%A7%BB%E9%99%A4%E5%BC%80%E6%9C%BA%E9%A1%B9)
        - [Systemd的启动顺序](#systemd%E7%9A%84%E5%90%AF%E5%8A%A8%E9%A1%BA%E5%BA%8F)
- [Tomcat和JDK安装](#tomcat%E5%92%8Cjdk%E5%AE%89%E8%A3%85)
    - [环境描述：](#%E7%8E%AF%E5%A2%83%E6%8F%8F%E8%BF%B0)
    - [可用本地电脑下载jdk1.81.可用本地电脑下载jdk1.8](#%E5%8F%AF%E7%94%A8%E6%9C%AC%E5%9C%B0%E7%94%B5%E8%84%91%E4%B8%8B%E8%BD%BDjdk181%E5%8F%AF%E7%94%A8%E6%9C%AC%E5%9C%B0%E7%94%B5%E8%84%91%E4%B8%8B%E8%BD%BDjdk18)
    - [安装上传工具2.安装上传工具](#%E5%AE%89%E8%A3%85%E4%B8%8A%E4%BC%A0%E5%B7%A5%E5%85%B72%E5%AE%89%E8%A3%85%E4%B8%8A%E4%BC%A0%E5%B7%A5%E5%85%B7)
    - [jdk上传OK后解压](#jdk%E4%B8%8A%E4%BC%A0ok%E5%90%8E%E8%A7%A3%E5%8E%8B)
    - [jdk环境变量配置](#jdk%E7%8E%AF%E5%A2%83%E5%8F%98%E9%87%8F%E9%85%8D%E7%BD%AE)
    - [更新profile文件](#%E6%9B%B4%E6%96%B0profile%E6%96%87%E4%BB%B6)
    - [查看java版本](#%E6%9F%A5%E7%9C%8Bjava%E7%89%88%E6%9C%AC)
    - [下载tomcat8](#%E4%B8%8B%E8%BD%BDtomcat8)
    - [上传tomcat8并解压](#%E4%B8%8A%E4%BC%A0tomcat8%E5%B9%B6%E8%A7%A3%E5%8E%8B)
        - [启动tomcat](#%E5%90%AF%E5%8A%A8tomcat)
    - [页面验证](#%E9%A1%B5%E9%9D%A2%E9%AA%8C%E8%AF%81)
    - [此为防火墙在开启状态，访问被阻，关闭防火墙或者允许页面端口通过都可以。](#%E6%AD%A4%E4%B8%BA%E9%98%B2%E7%81%AB%E5%A2%99%E5%9C%A8%E5%BC%80%E5%90%AF%E7%8A%B6%E6%80%81%E8%AE%BF%E9%97%AE%E8%A2%AB%E9%98%BB%E5%85%B3%E9%97%AD%E9%98%B2%E7%81%AB%E5%A2%99%E6%88%96%E8%80%85%E5%85%81%E8%AE%B8%E9%A1%B5%E9%9D%A2%E7%AB%AF%E5%8F%A3%E9%80%9A%E8%BF%87%E9%83%BD%E5%8F%AF%E4%BB%A5)
    - [生产环境建议开启端口即可，增强服务器安全性：](#%E7%94%9F%E4%BA%A7%E7%8E%AF%E5%A2%83%E5%BB%BA%E8%AE%AE%E5%BC%80%E5%90%AF%E7%AB%AF%E5%8F%A3%E5%8D%B3%E5%8F%AF%E5%A2%9E%E5%BC%BA%E6%9C%8D%E5%8A%A1%E5%99%A8%E5%AE%89%E5%85%A8%E6%80%A7)
    - [久违的tomcat页面显示OK](#%E4%B9%85%E8%BF%9D%E7%9A%84tomcat%E9%A1%B5%E9%9D%A2%E6%98%BE%E7%A4%BAok)
    - [部署遇到问题](#%E9%83%A8%E7%BD%B2%E9%81%87%E5%88%B0%E9%97%AE%E9%A2%98)

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
**感激分享**

[关于守护线程与线程池的关闭(shutdown)]https://www.cnblogs.com/fxtx/p/11008471.html

[Springboot项目启动时运行特定方法，项目关闭时执行特定操作]https://blog.csdn.net/qq_38361800/article/details/95943547

[tomcat关闭后线程依然运行解决办法，设置线程为守护线程]https://blog.csdn.net/p312011150/article/details/81365087

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
