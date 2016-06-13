## 安装和启动过程简介

### 安装过程

SOMA平台目前发布的最新版本是2.0.1，安装的过程分为手动安装和一键式安装。手动安装中 SOMA平台分两个服务器，Controller是使用业务时所必须的基础服务器，Ma是监控基础数据的服务器，安装 SOMA平台的标准过程如下：

1.  安装消息队列和缓存服务器—redis(QUEUE)
2.  安装基础数据库posgresql(CMDB)
3.  安装软件仓库(REPO)
4.  安装controller(CTRL)
5.  安装ma(MA)

手动安装按照如上1-5的顺序逐步进行即可。一键式安装的过程如下：

1） 一键式安装消息队列和缓存服务器—redis(QUEUE)、基础数据库posgresql(CMDB)、controller(CTRL)、ma(MA)、软件仓库(REPO)

一键式安装具体内容请参考4.6小节。

### 启动过程

按照如上的步骤完成安装之后需要对各个服务器进行启动，启动的顺序必须为：

1.  队列和缓存服务器—redis(QUEUE)
2.  数据库posgresql(CMDB)
3.  软件仓库(REPO)
4.  controller(CTRL)
5.  ma(MA)

controller和ma作为核心运行的组件必须最后依次进行启动，否则会出现因为无法连接redis或者postgresql的问题系统无法正常运行。