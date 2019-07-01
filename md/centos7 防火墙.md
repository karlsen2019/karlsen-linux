# centos7 防火墙

## 开放防火墙

* 开放端口：`firewall-cmd --zone=public --add-port=6379/tcp --permanent`
* 重新加载：`firewall-cmd --reload`
* 查看开放端口列表：`firewall-cmd --list-ports`

#### 禁用防火墙

* `systemctl disable firewalld.service`