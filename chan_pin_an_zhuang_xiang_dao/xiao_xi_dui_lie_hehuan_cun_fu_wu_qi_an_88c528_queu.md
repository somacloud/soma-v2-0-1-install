## 消息队列和缓存服务器安装(QUEUE) {#queue}

消息队列和缓存服务器支持在windows和linux系统下的安装。

### windows环境下安装 {#windows}

1）拷贝安装文件。Windows环境下Redis的安装包为安装盘windows目录中的Redis3.zip。拷贝该文件到安装目录下并解压为Redis3。

2）启动redis。以“管理员的身份”打开CMD进入Redis3目录执行redis-server.exe redis.windows.conf。如图04-01所示。

图4-01 windows下redis启动

### linux环境下安装 {#linux}

1）在根目录新建文件文件夹amp；在后面linux环境下的安装会陆续用到该文件夹。

mkdir /amp

2）将redis安装包拷贝到amp文件夹中，并解压安装包。

tar –xzf /amp/redis-3.0.2.tar.gz

3）进入redis-3.0.2文件夹并执行安装命令。

cd /amp/redis-3.0.2

make

可能出错

| [root@QST-AMP-3 redis-3.0.2]# make |
| --- |

此时使用 make MALLOC=libc

4）修改/amp/redis-3.0.2/redis.conf文件。

vi /amp/redis-3.0.2/redis.conf

将stop-writes-on-bgsave-error yes 改为 stop-writes-on-bgsave-error no

将# maxmemory&lt;bytes&gt;改为maxmemory8gb

将 save 900 1 改为 #save 900 1

将 save 300 10 改为 #save 300 10

将 save 60 10000 改为 #save 60 100000

将 # maxmemory-policy volatile-lru改为maxmemory-policy volatile-lru

5）修改/etc/sysctl.conf文件。

vi /etc/sysctl.conf

在文件末尾加上vm.overcommit_memory=1

6）手动执行命令，使修改生效。

sysctlvm.overcommit_memory=1

7）启动服务redis服务。

cd /amp/redis-3.0.2/src

nohup ./redis-server ../redis.conf &

8）查看服务启动状况。

tail –f nohup.out

若出现下图，则说明redis启动成功

图4-02 Linux下redis启动