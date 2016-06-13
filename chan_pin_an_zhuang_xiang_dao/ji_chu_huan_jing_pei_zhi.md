## 基础环境配置

### 防火墙配置 {#-0}

在linux环境下，由于系统特性，需要一些防火墙的配置。若在防火墙启动时，需要添加以下配置。

1.  修改/etc/sysConfig/iptables文件，添加如下内容。

-A INPUT -m state --state NEW -m tcp -p tcp --dport 6379 -j ACCEPT

-A INPUT -m state --state NEW -m tcp -p tcp --dport 80 -j ACCEPT

-A INPUT -m state --state NEW -m tcp -p tcp --dport 5432 -j ACCEPT

其中如果controller的端口有修改，需要把第二行中的80改为4.4小节中配置的controller端口。

1.  重新启动防火墙。

service iptables restart

在windows环境下，由于系统特性，如果需要进行跨网络或者跨机器访问时则会有防火墙的限制，这时需要关闭防火墙或者开放本地的controller访问端口（4.4小节中配置过得controller的端口）。

### 安装完成说明 {#-1}

当按照1.2.1的安装过程完成安装，并按照1.2.2完成启动之后，则soma平台的安装工作就已经结束了，为了验证是否安装完整或者是否安装成功则需要进行平台的访问验证。具体的方式为：在本机或者同一网段的主机（必须要将soma平台所在的主机关闭防火墙或者开放本地的controller访问端口）的浏览器上访问http://{ip}:{port}/soma/，其中ip为4.4节中配置好的controller的ip地址和端口，访问之后会出现如下的界面，之后通过输入用户名（默认为admin）和密码（默认为111111）即可进行平台的访问，访问界面如图4-25所示。

图4-25 soma平台访问界面