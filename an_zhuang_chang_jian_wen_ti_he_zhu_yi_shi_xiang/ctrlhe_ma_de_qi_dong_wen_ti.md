## CTRL和MA的启动问题 {#ctrl-ma}

启动CTRL时，当执行startController.sh时，可能会出现: ./startController.sh：Permission denied的错误。这是因为对startController.sh没有执行的权限。

解决方法：执行命令

chmod +x startController.sh

对该文件赋予执行的权限，即可。

重新启动CTRL。此时，可能会出现:/amp/cloudcontroller/jdk/jre/bin/java:Permission denied的错误。

解决方法：进入/amp/cloudcontroller/jdk/jre/bin文件夹，执行命令

Chmod +x *

对该文件夹中的所有文件赋予执行权限，即可。

在启动MA时遇到类似的错误时，按照同样的方法解决。