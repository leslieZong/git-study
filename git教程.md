# Git教程

​					--------------------总结自廖雪峰Git教程  https://www.liaoxuefeng.com/wiki/896043488029600/

## 1.安装git

官网下载git[下载安装程序](https://git-scm.com/downloads)

安装完成后，在开始菜单里找到“Git”->“Git Bash”，蹦出一个类似命令行窗口的东西，就说明Git安装成功！

![install-git-on-windows](https://www.liaoxuefeng.com/files/attachments/919018718363424/0)

安装完成后，还需要最后一步设置，在命令行输入：

```
$ git config --global user.name "Your Name"
$ git config --global user.email "email@example.com"
```

注意`git config`命令的`--global`参数，用了这个参数，表示你这台机器上所有的Git仓库都会使用这个配置，当然也可以对某个仓库指定不同的用户名和Email地址。

## 2.创建版本库

### 2.1创建文件夹及文件

```
$ mkdir learngit
$ cd learngit
$ pwd
/Users/michael/learngit
```

### 2.2初始化    git init

如果你没有看到`.git`目录，那是因为这个目录默认是隐藏的，用`ls -ah`命令就可以看见

## 3.提交代码

### 3.1第一步，用命令`git add`告诉Git，把文件添加到仓库：

```
$ git add readme.txt

//添加所有改动的文件
git add .
```

### 3.2第二步，用命令`git commit`告诉Git，把文件提交到仓库：

```
$ git commit -m "注释"
```

`git status`命令可以让我们时刻掌握仓库当前的状态

`git diff`顾名思义就是查看difference，显示的格式正是Unix通用的diff格式

`git log`命令显示从最近到最远的提交日志，

`git reflog`用来记录你的每一次命令

提交后，用`git diff HEAD -- 文件名`命令可以查看工作区和版本库里面最新版本的区别

## 4.撤销修改

场景1：当你改乱了工作区某个文件的内容，想直接丢弃工作区的修改时，用命令`git restore <file>`。

场景2：当你不但改乱了工作区某个文件的内容，还添加到了暂存区时，想丢弃修改，分两步，第一步用命令`git restore --staged <file>`，就回到了场景1，第二步按场景1操作。

场景3：已经提交了不合适的修改到版本库时，想要撤销本次提交，参考[版本回退](https://www.liaoxuefeng.com/wiki/896043488029600/897013573512192)一节，不过前提是没有推送到远程库。

## 5.删除文件
