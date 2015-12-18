比较常用的LNMP环境配置
======================================================


## 1 描述
根据自己CentOS7.1服务器下Nginx、MySql和PHP的配置和脚本文件整理。

## 2 版本更新说明
初始版本是根据文章[《2015年博客升级记》](https://typecodes.com/mix/2015updateblog.html '查看原文')写的。整个目录如下：

	|Project_dir
	|
	|         |----nginx.conf      配置文件
	|--Nginx--|
	|         |----nginx	       服务控制脚本
	|
	|         |----php.ini		   配置文件
	|         |----php-fpm	       服务控制脚本
	|---PHP---|
    |         |----php-fpm.conf    配置文件
	|		  |----www.conf        配置文件
	|
	|         |----my.cnf          配置文件
	|--MySql--|
	|         |----mysqld	       服务控制脚本
	|
	|--README.md


###2.1 版本v1.0.0.1

根据博客的文章说明，这个版本的内容包括：Nginx配置文件和服务控制脚本、PHP配置文件和控制脚本以及Mysql的配置文件。

##### 2.1.1 Nginx目录

nginx.conf配置文件： [《2015博客升级记(六)：Nginx配置HTTPS和SPDY实战》](https://typecodes.com/web/centos7nginxhttpsspdy.html '查看原文')

nginx服务控制脚本： [《Nginx服务启动、停止和重启等操作的SHELL脚本》](https://typecodes.com/web/nginxserviceoptshell.html '查看原文')

##### 2.1.2 PHP目录

php.ini、php-fpm.conf和www.conf配置文件： [《PHP7中php.ini、php-fpm和www.conf的配置》](https://typecodes.com/web/php7configure.html '查看原文')

php-fpm服务控制脚本： [《PHP7服务启动、停止和重启等操作的SHELL脚本》](https://typecodes.com/web/php7serviceoptshell.html '查看原文')

##### 2.1.3 MySql目录

my.cnf配置文件： [《CentOS系统MySQL的配置文件my.cnf》](https://typecodes.com/web/centosmysqlconfig.html '查看原文')

mysqld服务控制脚本： [《MySql服务启动、停止和重启等操作的SHELL脚本》](https://typecodes.com/web/mysqldserviceoptshell.html '查看原文')


###2.2 版本v1.0.0.2

-----2015.11.14 00:05更新 `php.ini` 文件：

	1、由于每次升级编译PHP版本的时候，都会在extensions目录下产生对应的动态库文件夹。因此，为了避免每次都修改配置文件，建议把对应版本的动态库文件夹下的所有动态库文件都复制到extensions根目录下。

-----2015.12.18 12:52添加 `nginx_log_backup.sh` 文件：

	1、可用于备份Nginx、MySQL和PHP的日志以及其它Linux下的应用产生的日志；

该脚本详细说明见：[《Linux下Nginx、MySQL和PHP等应用的日志切割脚本》](https://typecodes.com/linux/applogsbackup.html '查看原文')

-----2015.12.18 15:22添加 `nginx_pelican.conf` 文件：

	1、对于pelican这种静态HTML博客，由于不需要和PHP通信，所以把nginx.conf中的PHP配置部分去掉了。使用时，将其重命名为nginx.conf即可。