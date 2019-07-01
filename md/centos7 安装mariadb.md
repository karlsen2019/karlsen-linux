# centos7 安装mariadb

* 查看mariadb是否安装
```shell
rpm -qa | grep mariadb
rpm -qa | grep mariadb-server
```
> 默认mariadb已经安装，mariadb-server未安装

![](http://ww1.sinaimg.cn/large/007EE6nYly1g0ug17c5r0j30am02ua9y.jpg)

* 安装mariadb-server
  * `yum install mariadb-server -y`
* mariadb相关操作
  * 启动：
    * `systemctl start mariadb`
  * 查看状态：
    * `systemctl status mariadb`
  * 停止：
    * `systemctl stop mariadb`

* mariadb设置开机启动
  * `systemctl enable mariadb`

* 基本设置
  * `mysql_secure_installation`

* 设置远程访问权限
  * 登录linux mariadb
  * `grant all privileges  on *.* to root@'%' identified by "s04220501229";`
