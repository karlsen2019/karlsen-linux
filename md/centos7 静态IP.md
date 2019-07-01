# centos7 静态IP

1. 使用ftp工具下载网卡配置文件，`ifcfg-eno16777736`
   * 路径：`/etc/sysconfig/network-scripts`
2. 将 `ifcfg-eno16777736` 内容替换为：

```shell
TYPE="Ethernet"
BOOTPROTO="none"
DEFROUTE="yes"
IPV4_FAILURE_FATAL="no"
IPV6INIT="yes"
IPV6_AUTOCONF="yes"
IPV6_DEFROUTE="yes"
IPV6_FAILURE_FATAL="no"
NAME="eno16777736"
DEVICE="eno16777736"
ONBOOT="yes"
IPADDR="192.168.245.132"
PREFIX="24"
GATEWAY="192.168.245.2"
DNS1="192.168.245.2"
IPV6_PEERDNS="yes"
IPV6_PEERROUTES="yes"
IPV6_PRIVACY="no"
```

> 1. 需要更改，`IPADDR`,`GATEWAY`,`DNS1`。
> 2. `245`为net8网卡的网段，每次安装vmware都不一样。

3. 使用ftp工具覆盖网卡配置文件。
4. 重启网卡：`service network restart`