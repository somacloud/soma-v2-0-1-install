## redis安装错误 {#redis}

初次安装redis时，执行make命令时可能会出现error:gcc相关的错误，需要安装gcc相关的工具。执行如下命令（注意：在安装gcc之前需要保证yum源已经安装，即yum命令可执行）:

yum install gcc

注意:安装完成以后，将已经安装redis相关文件删除后，重新开始安装，否则会出现安装错误。