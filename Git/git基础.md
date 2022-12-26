# **Git**



## **单独设置用户名/邮箱：**

git config user.name "这里是用户名"

git config user.email "这里是你的邮箱"



**执行以下命令可以查看设置是否成功**

git config --list



## **1.1 基本配置**

- ​		git --version：返回版本号
- ​		git --help：帮助文档
- ​		git config --list：查看所有配置
- ​		git config --list --show-origin：查看所有配置以及它们所在的文件
- ​		git config --global user.name "用户名"：全局配置用户名
- ​		git config --global user.email 邮箱地址：全局配置邮箱
- ​		git config user.name：查看用户名
- ​		git config user.email：查看邮箱
- 

## **1.2 基本操作**

- ​		git status ：查看仓库状态
- ​		git init：创建一个空仓库，或者重新初始化一个已有仓库
- ​		git add：把文件添加到可提交列表（临时缓冲区）
- ​		git commit：提交改动（增删改）至仓库
- ​		git log：打印提交日志
- ​		git branch：查看、添加、删除分支
- ​		git checkout：切换分支、标签
- ​		git merge：合并分支
- ​		git tag：新建、查看标签
- ​		git clone：下载仓库
- 


## 上传操作
git init  // 初始化本地仓库

git add readme.md // 添加要上传的文件 

git add * // 加入该文件夹下所有项目

git status // 检查状态，如果文件的状态都为绿色，证明成功

git commit -m "first commit" // 提交到仓库，并写一些注释

git remote add origin https://github.com/zhangbx0128/paryblog.git //修改下地址

git push -u origin master // 将本地仓库的东西提交到origin的地址，master分支下