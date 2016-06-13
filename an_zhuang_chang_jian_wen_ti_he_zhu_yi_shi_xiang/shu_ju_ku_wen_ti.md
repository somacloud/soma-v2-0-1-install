## 数据库问题

1.启动controller时，出现Error: permission denied for relation cc_computer的错误提示。解决方法是在amp数据库中执行如下命令

Grant select on table cc_computer to postgres

其中，to后面的用户名为数据库连接的用户。

2.若无法连接数据库，请在修改数据库配置文件后重启数据库或检车数据库所在主机的防火墙是否关闭。