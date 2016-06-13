## 软件仓库安装

软件仓库的安装是需要有java的环境支持，所以在安装软件仓库之前请务必要确保本地系统有安装好的java环境（windows和linux都需要），即保证java命令的可执行，否则可能会出现无法正常暗转的情况，这里jdk版本需要在1.6及以上，并且jdk的安装路径中不能出现空格如：

C:\Program Files\Java\jdk1.7.0_79（Program和Files中间有空格）。

另外，如果有独立运行软件仓库的需求，那么只要通过如下的windows/linux环境下的安装指导即可完成安装，若是不想安装软件仓库或者使用现成的软件仓库，那么我们也默认地提供了几个默认的安装源，这时只需要同步一下数据库即可进行软件仓库的访问，具体的操作过程请看4.3.3小节。

### windows环境下安装 {#windows}

软件仓库的安装包为windows目录下的repo-bundle-template-2.7.2-03-bundle.zip。

1）创建repo文件夹，该文件夹为软件仓库的安装位置。

2）将安装包解压到repo文件夹中，得到两个文件目录分别为repo-bundle-template-2.7.2-03和sonatype-work。

图4-14 windows下repo安装目录列表

3）执行软件仓库安装和启动。以管理员身份运行命令行窗口CMD，并进入到目录repo\ repo-bundle-template-2.7.2-03\bin下并执行命令repo.bat install。

安装完成之后继续执行repo.bat start启动该服务。

图4-15 windows下repo服务启动

4）访问repo服务。在浏览器中输入http://{ip}:8081/repo/，安装如果成功的话会出现如图所示界面。

图4-15 windows下repo服务访问

5）repo服务操作。Windows下repo服务的操作主要是通过repo\ repo-bundle-template-2.7.2-03\bin目录下的repo.bat文件来进行的主要的操作有repo.bat uninstall/install/stop/start。如果已经在windows上安装过repo服务之后还需重装，需要先后通过repo.bat stop/uninstall进行停止/卸载。

### linux环境下安装 {#linux}

软件仓库的安装包linux目录下的repo-bundle-template-2.7.2-03-bundle.zip。

1）在amp文件夹中创建repo文件夹。

2）将安装包解压到repo文件夹中，并建立同步链接。

cp repo-bundle-template-2.7.2-03-bundle.zip repo/

cd repo

unzip repo-bundle-template-2.7.2-03-bundle.zip

ln –s /amp/repo/repo-bundle-template-2.7.2-03 repo

3）添加用户并授权。

useradd

passwd

chown –R : .

4）修改环境变量。

vi /etc/init.d/repo

修改如下内容：

| JAVA_HOME=/cloud/coord/cloudagent/jre #修改为自己的JAVA_HOME |
| --- |

5）启动服务。

service repo start

### 默认软件仓库初始化 {#-0}

当前在提供了独立安装软件仓库的同时也提供了默认访问的软件源，默认的软件源的访问方式有3种，分别是内网访问，办公网访问和外网访问。可以通过如下的方式进行默认软件源的初始化。该步执行初始化的前提是必须完成controller的安装。如果没有完成controller的安装请先参照4.4小节完成安装，如果完成了controller的安装，那么就可以继续进行如下操作。

以管理员（windows环境）/root权限（linux环境）的权限进入controller的安装目录cloudcontroller，并进入bin目录下执行

updateDB.bat \script\x（windows环境）

updateDB.bat /script/x（linux环境）

其中，x代表如下表中的某个sql文件，具体的表对与网络的对应关系如表4-01所示：

| 表名 | 对应网络 |
| --- | --- |
| repo_bg.sql | 办公网 |
| repo_nw.sql | 内网 |
| repo_ww.sql | 外网 |

表4-01 sql文件与网络的对应关系

比如您需要的软件源访问网络为内网您的环境为windows，则你需要以管理员身份打开CMD在安装目录cloudcontroller的bin目录下执行updateDB.bat \script\ repo_nw.sql。其他的类似。就不多做说明。另外，查看软件源的方式为，登录soma平台（前提是必须soma平台安装和启动完成），在“目录”->“软件源”菜单栏中即可查看到当前平台所拥有的软件源信息。