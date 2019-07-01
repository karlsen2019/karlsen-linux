# centos7 安装单节点redis

> 由于是在vmware中安装，所以首先要配置虚拟机相关环境，网络接口使用NAT。

#### 虚拟机环境配置

1. 静态IP,可参考[centos7 静态IP](https://blog.csdn.net/sauyer/article/details/88079999)
2. 主机名：`hostnamectl set-hostname redis-single`
3. gcc环境：`yum -y install gcc tcl –y`

#### redis编译及安装

1. 上传redis压缩包到：`/usr/local/src`
2. 解压：`tar -xvf redis-3.2.6.tar.gz`
3. 进入redis根目录：`cd /usr/local/src/redis-3.2.6`
4. 编译：`make`
5. 安装：`make PREFIX=/opt/sauyer/redis install`

#### 环境变量配置

1. `/etc/profile`加入

```shell
export REDIS_HOME=/opt/sauyer/redis
export PATH=$PATH:$REDIS_HOME/bin
```

2. `wq`，重新加载`. /etc/profile`

#### redis服务安装

1. 进入utils目录：`cd /usr/local/src/redis-3.2.6/utils/`
2. 执行安装文件：`./install_server.sh`
![](http://ww1.sinaimg.cn/large/007EE6nYly1g0oqis2lqmj30ha0eb0te.jpg)
3. 进入redis客户端：`redis-cli`

#### 开放防火墙

* 开放端口：`firewall-cmd --zone=public --add-port=6379/tcp --permanent`
* 重新加载：`firewall-cmd --reload`
* 查看开放端口列表：`firewall-cmd --list-ports`

#### 配置redis可远程访问

1. 打开redis配置文件：`vim /etc/redis/6379.conf`
2. 更改相关配置
   1. 去除绑定ip
   2. 关闭保护模式
   3. 开启守护线程，后台启动
   4. 持久化方式改为aof

```shell
#bind 127.0.0.1
protected-mode no
daemonize yes
appendonly yes
appendfsync always
```

#### 相关操作命令

* 查看：`service redis_6379 status`
* 停止：`service redis_6379 stop`
* 启动：`service redis_6379 start`
* 重启：`service redis_6379 restart`