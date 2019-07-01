# centos7 git安装及配置

## 安装

* 安装依赖库：`yum install curl-devel expat-devel gettext-devel openssl-devel zlib-devel`
* 使用wget下载git源码包
  * 下载地址：[Releases · git/git · GitHub](https://github.com/git/git/releases)
  * wget：`wget https://github.com/git/git/archive/v2.21.0-rc2.tar.gz`
* 安装
```shell
tar -zxf v2.21.0-rc2.tar.gz
cd git-2.21.0-rc2/
make prefix=/usr/local all
sudo make prefix=/usr/local install
```

## 配置

### 命令别名

```shell
alias gs="git status"
alias gd="git diff"
alias gc="git checkout"
alias ga="git add"
alias gcm="git commit -m"
alias gb="git branch"
alias gp="git pull"
alias gl="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
```

### 查看邮箱配置

```shell
git config user.email
```

### 用户名配置

```shell
git config --global user.name  "sauyer.ming"
```

### 工作邮箱

```shell
git config --global user.email "sauyer855975125205@outlook.com"
```

### 个人邮箱

```shell
git config --global user.email "sauyer.ming@gmail.com"
```

### 永久保存凭证
```
git config --global credential.helper store
```


