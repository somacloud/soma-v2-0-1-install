## CTRL和MA的配置问题 {#ctrl-ma}

如果不能使用sysConfig.bat或者sysConfig.sh启动的图形界面进行数据库、消息队列和安全令牌的配置，则需要手动修改相关文件。主要修改下面两个文件:

1.  discache.xml文件

将其中红色部分的IP地址改为Redis安装机器的IP。

将其中蓝色部分的IP地址改为SSP云端Redis安装机器的IP。

1.  prop.xml文件

主要修改两部分内容。一是数据库的相关配置，如下图中的红色部分；databaseUrl>jdbc:postgresql://20.12.3.142:5432/amp&lt;/databaseUrl&gt;中的IP配置为数据库安装所在机器的IP,后面的amp为使用的数据库，修改为安装数据库时新建的amp数据库。&lt;user&gt;coord_dxd&lt;/user&gt;和&lt;password&gt;1&lt;/password&gt;中红色部分分别修改为数据的用户名和密码。二是在数据库配置后面添加蓝色部分，手动添加平台的安全令牌。