## MA安装 {#ma}

### windows环境下安装 {#windows}

windows环境下的安装包为coord_ma.exe。安装步骤如下：

1.  将文件coord_ma.exe拷贝到待安装目录并点击打开文件，得到ma文件夹。
2.  将controller中的discache.xml和prop.xml文件拷贝至/ma/ierp/bin文件夹中。
3.  修改/ma/ierp/bin中的monitorconf.xml文件。将其中的cc_host和cc__port改为controller所在的IP地址和端口（同4.4.1小节7）中的端口号一致）。
4.  启动ma。执行/ma中的startMa.bat文件。
5.  启动logcat。执行/ma/logcat中的startup.bat文件。
6.  停止logcat。执行/ma/logcat中的stop.bat文件。
7.  停止ma。执行/ma中的stopMa.bat文件。

### linux环境下安装 {#linux}

linux环境下的安装包为coord_ma.tar。安装步骤如下：

1.  在目录amp中解压coord_ma.tar文件，得到ma文件夹。
2.  将controller中的discache.xml和prop.xml文件拷贝至/ma/ierp/bin文件夹中。
3.  修改/ma/ierp/bin中的monitorconf.xml文件。将其中的cc_host和cc__port改为controller所在的IP地址和端口（同4.4.2小节7）中的端口号一致）。
4.  启动ma。执行/ma中的startMa.sh文件。
5.  启动logcat。执行/ma/logcat中的startup.sh文件。
6.  停止logcat。执行/ma/logcat中的stop.sh文件。
7.  停止ma。执行/ma中的stopMa.sh文件。