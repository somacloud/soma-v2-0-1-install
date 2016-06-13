## 一键式安装

一键式安装需要有jdk的支持，无论是在windows环境下还是在linux的环境下，所以安装之前请确保jdk（版本在1.6之上）以安装并配置（注意：jdk路径中不能带有空格）。

### windows环境下安装 {#windows}

windows环境下的安装目录为盘中的windows。安装步骤如下：

1.  拷贝文件。将文件目录windows拷贝到待安装服务器。
2.  修改配置。进入windows目录下的setup目录，并阅读Readme.txt文件，按照自己的环境进行配置，修改配置文件env.prop。其中，配置项如表4-02所示。

| 编号 | 参数名 | 默认值 | 说明 |
| --- | --- | --- | --- |
| 1 | PRO_NAME |  | 项目名（必须修改） |
| 2 | INSTALL_DIR | C:\ucloud | 软件安装位置（根据主机配置修改，不建议放C盘） |
| 3 | POSTGRES_DIR | C:\postgresql | 数据库安装位置（不建议放C盘） |
| 4 | REDIS_PORT | 6379 | 消息队列、缓存端口（不建议修改） |
| 5 | POSTGRES_PORT | 5432 | 数据库端口（不建议修改） |
| 6 | POSTGRES_NAME | soma | 数据库名（不建议修改） |
| 7 | POSTGRES_USER | soma | 数据库用户名（不建议修改） |
| 8 | POSTGRES_PWD | soma | 数据库密码（根据自己要求修改） |
| 9 | CONTROLLER_RCPORT | 7681 | 应用访问端口（不建议修改） |
| 10 | SSP_CONNECT | ts.yonyou.com | 云端访问地址（不能修改） |
| 11 | LOCAL_IP |  | 本机ip地址（必须修改为本机IP） |
| 12 | SOCKET_HOST_LAN |  | 同上 |
| 13 | SOCKET_HOST |  | 本机外网ip（必须修改） |
| 14 | SOCKET_PORT | 5044 | 日志服务器端口（不建议修改） |
| 15 | SOCKET_PORT_ZIP | 5046 | 日志服务器端口（不建议修改） |

表4-02 windows一键式安装环境变量配置

1.  启动一键式安装。修改setup目录下的setup.bat.backup文件为setup.bat。以管理员身份执行（右键点击文件“以管理员身份运行”）。安装过程需要一定时间请耐心等待。

### linux环境下安装 {#linux}

linux环境下的安装目录为linux。安装步骤如下：

1.  拷贝文件。将目录linux拷贝到待安装服务器。
2.  环境变量配置。修改env_default.prop配置文件。环境变量具体的配置详情如表4-03所示。

| 编号 | 参数名 | 默认值 | 说明 |
| --- | --- | --- | --- |
| 1 | CONTROLLER_IP | 6379 | 本机ip地址（必须修改为本机IP） |
| 2 | POSTGRES_ADDR |  | 同CONTROLLER_IP |
| 3 | POSTGRES_PORT | 5432 | 数据库端口（不建议修改） |
| 4 | POSTGRES_NAME | soma | 数据库名（不建议修改） |
| 5 | POSTGRES_USER | soma | 数据库用户名（不建议修改） |
| 6 | POSTGRES_PWD | soma | 数据库密码（根据自己要求修改） |
| 7 | REDIS_ADDR |  | 同CONTROLLER_IP |
| 8 | REDIS_PORT | 6379 | 消息队列、缓存端口（不建议修改） |
| 9 | CONTROLLER_RCPORT | 7681 | 应用访问端口（不建议修改） |
| 10 | SSP_CONNECT | ts.yonyou.com | 云端访问地址（不能修改） |
| 11 | SOCKET_HOST_LAN |  | 同CONTROLLER_IP |
| 12 | SOCKET_HOST |  | 本机外网ip（必须修改） |
| 13 | SOCKET_PORT | 5044 | 日志服务器端口（不建议修改） |
| 14 | SOCKET_PORT_ZIP | 5046 | 日志服务器端口（不建议修改） |
| 15 | PRO_NAME |  | 项目名（必须修改） |

表4-03 linux一键式安装环境变量配置

1.  启动一键式安装。进入linux目录阅读Readme.txt。修改当前目录下setup.sh.backup文件为setup.sh，具体操作为

mv setup.sh.backup setup.sh

赋予当前目录文件夹下修改后的setup.sh文件可执行权限:

chmod u+x *.sh

以root权限运行setup.sh脚本。