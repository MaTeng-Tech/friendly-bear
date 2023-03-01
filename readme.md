### Git学习笔记

[TOC]

#### 1. 配置个人信息 

在开始使用 `git` 之前，需要配置 `name` 和 `email` ，即让 `git` 版本库知道你是谁。

```shell
	git config --global user.name "Your Name" 
	git config --global user.email "email@example.com" 
	git config user.name     # 查看配置的姓名
	git config user.email    # 查看配置的邮箱
```

#### 2. 工作区、暂存区和版本库

工作区 **Working Directory**:  即本地可以看到编辑的目录。

暂存区 **stage**:  介于工作区到版本区之间。先添加 `git add` 进暂存区再提交 `git commit` 到版本库

版本库 **Repository**:  工作区目录下的 `.git` （默认为隐藏目录）

#### 3. 一个小示例

1. 初始化版本库 

```shell
	git init      # 初始化版本库
	# 创建成功：Initialized empty Git repository in E:/Desktop/git test/.git/
	# 当前工作区目录下会多出.git文件夹，用于跟踪管理版本库
```

2. 添加指定文件到暂存区中

```shell 
	git add file.py   
	# 若没有提示，表示提交成功
	# 若未初始化会提示：fatal: Not a git repository (or any of the parent directories): .git
	# 提交失败会提示：fatal: pathspec 'x.txt' did not match any files
```
3. 查看文件是否提交成功
```shell
	git status
	# 红色表示在工作区 即未提交至暂存区
	# 绿色表示在暂存区
```
4. 提交暂存区所有文件到版本区
```shell
	git commit -m 'message'
```

#### 4. GitHub远程仓库

##### 4.1 场景一：关联

关联，即本地有仓库，要与远程仓库做关联。

##### 4.2 场景二：推送 `git push`

推送，即本地有仓库有内容，要推送给远程仓库。

##### 4.3 场景三：拉取 `git pull ` / `git fetch `

拉取，即本地有仓库有内容，拉取远程仓库新内容。

##### 4.4 场景四：克隆 `git clone`

克隆，即本地无仓库，要获取一个完整的远程仓库。

```shell
	# 只有第一次获取远程仓库时需要克隆
    git clone https://github.com/xxx.git
```



```shell
	git remote add origin https://github.com/MaTeng-Tech/friendly-bear.git
	git remote remove origin
	git remote add origin git@github.com:MaTeng-Tech/friendly-bear.git
	git remote -v
	git push -u origin master
```

