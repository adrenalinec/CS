# Git



git基本操作

```bash
git status

git add .
git commit -m "add some new messages"

git clone URL
git init	#在当前目录建立git仓库
git push
 
 
 //git修改仓库名字
 git remote -v 
 git remote set-url origin git@github.com:adrenalinecc/newname.git
 
 
 
 
 
ssh-keygen -trsa -C "Email" #配置本地ssh的公钥&私钥来进行无密码push操作
```





git 忽略文件



.gitignore

```sh
*.txt 	#忽略所有txt文件
build/ 	#忽略build目录下的所有文件
```







# git分支



- 主分支
- 不同版本的分支
- 开发用分支



```shell
git branch 
git branch -r	#看远程分支
git checkout -b 	
git merge [branch]
git push 
```









# Github SSH[^ 1 ]





```bash
git remote -v	#origin是默认repository名称，master是默认的主分支名称
							#这条命令检测和仓库的联系，必须在git仓库下才能执行
							
ssh -T git@github.com	#	检测和Github账号的联系

git config --local -e	#在repo内部查看配置，之后可以更改URL来多账号登陆



vim ~/.ssh/config

#turbofinance
Host turbo
   HostName github.com
   User git
   IdentityFile ~/.ssh/turbo_rsa
   IdentitiesOnly yes

#adrenalinecc
Host adren
   HostName github.com
   User git
   IdentityFile ~/.ssh/adr_rsa
   IdentitiesOnly yes

#配置不同的github账号为不同的Host
#HostName都是github.com
#User都默认git
#IdentifyFile 选择对应的私钥
#IdentitiesOnly yes


#在repo中更改URl
git config --local -e

[core]
        repositoryformatversion = 0
        filemode = true
        bare = false
        logallrefupdates = true
        ignorecase = true
        precomposeunicode = true
[remote "origin"]
        url = git@adren:adrenalinecc/Mac.git    #更改这里，格式git@<Host>:repo
        fetch = +refs/heads/*:refs/remotes/origin/*
[branch "main"]
        remote = origin
        merge = refs/heads/main

#更改git URL 的地址 git@<Host>:repo

```







# Git SSH 加key



```bash
ssh-add -K ~/.ssh/id_rsa

#在多git配置中 只要把ID换下就行 对应的key只要没问题
```

















[^ 1 ]: （配置检测和多账号配置）

# Gitee

修改gitee和github的git push不用密码



```shell
git remote rm origin	#删除和远程的传递方式
git remote -v 				#查看和远程的通信方式
git remote add origin git@......git
git push origin master
```







# Gitlab

























# 备注



- Git commit的用户是根据下面的配置来判断的，并不是根据ssh密钥

  ```bash
  git config --global user.name 
  git config --global user.email 
  ```

  