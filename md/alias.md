# git配置

## 命令别名

```Java
alias gs="git status"
alias gd="git diff"
alias gc="git checkout"
alias ga="git add"
alias gcm="git commit -m"
alias gb="git branch"
alias gp="git pull"
alias gr="git reset --soft" 
alias gl="git log --graph --pretty=format:'%Cred%h%Creset -%C(yellow)%d%Creset %s %Cgreen(%cr) %C(bold blue)<%an>%Creset' --abbrev-commit"
    
alias cd-edm="cd /e/karlsen-worksapce/karlsen-edm" 
    
alias mvn-install="mvn clean install" 
alias mvn-package="mvn clean package" 
```

## 查看邮箱配置

```shell
git config user.email
```

## 用户名配置

```shell
git config --global user.name  
```

## 工作邮箱

```shell
git config --global user.email 
```


## 删除分支

* 本地分支删除：`git branch -d <branch>`
* 远程分支删除：`git push origin --delete <branchName>`
* 删除本地跟踪：`git branch -dr <remote>/<branch>`

## 修改远程地址

* `git remote rm origin`
* `git remote add origin [url]`

## git本地忽略已进入代码库的文件

* `git update-index --assume-unchanged .gitignore`
* `git update-index --no-assume-unchanged .gitignore`

## git修改注释

* `git commit --amend -m "New commit message"`

## git修改分支名

* `git branch -m old new`

## git同步远程分支

* `git remote prune origin`
* `git fetch -p`
