## 第一章 快速入门

### 1.1 什么是Git

* 文件夹拷贝
* 本地版本控制
* 集中式版本控制
* 分布式版本控制

### 1.2 为什么要做版本控制

要保留之前所有的版本，以便回滚和修改

### 1.3 安装Git

详见：

## 第二章 “东北热”创业史

### 2.1 第一阶段：单枪匹马

想要让git对一个目录进行版本控制需要以下步骤：

* 进入要管理的文件夹
* 执行初始化命令

```
git init
```

* 管理目录下的文件状态

```
git status
注：新增的文件和修改过后的文件都是红色
```

* 管理指定文件（红变绿）

```
git add 文件名
或git add .
```

* 个人信息配置：用户名、邮箱

```
git config --global user.name "Your Name"
git config --global user.email "You@example.com"
```

* 生成版本

```
git commit -m "描述信息"
```

* 查看版本记录

```
git log
或git reflog
```

### 2.2 第二阶段：拓展新功能

```
git add
git commit -m "短视频"
```

### 2.3 第三阶段：“约饭事件”

* 回滚至之前版本

```
git log
git reset --hard 版本号
```

* 回滚之后的版本

```
git reflog
git reset --hard 版本号
```

### 2.4 总结

```
git init
git add
git commit
git log
git reflog
git reset --hard 版本号
```

### 2.5 第四阶段：商城&紧急修复bug

#### 2.5.1分支

分支可以给使用者提供多个环境的可以，意味着你可以把你的工作从开发主线上分离开来，以免影响开发主线。

#### 2.5.2 紧急修复bug方案

![Snipaste_2021-01-16_20-32-53](C:\Users\11631\gitdir\image\Snipaste_2021-01-16_20-32-53.png)

#### 2.5.3 命令总结

* 查看分支

```
git branch
```

* 创建分支

```
git branch 分支名称
```

* 切换分支

```
git checkout 分支名称
```

* 分支合并（可能产生冲突）

```
git merge 要合并的分支

注意：切换分支再合并
```

* 删除分支

```
git branch -d 分支名称
```

#### 2.5.4 工作流

![Snipaste_2021-01-16_21-14-11](C:\Users\11631\gitdir\image\Snipaste_2021-01-16_21-14-11.png)



### 2.6 第五阶段：进军三里屯

```
1. 给远程仓库起别名
	git remote add origin 远程仓库地址
2. 向远程仓库推送代码
	git push -u origin 分支
```

到公司新电脑上第一次获取代码

```
1. 克隆远程仓库代码
	git clone 远程仓库地址（内部已实现 git remote add origin 远程仓库地址）
2. 切换分支
	git checkout 分支
```

在公司进行开发

```
1. 切换到 dev 分支进行开发
	git checkout dev
2. 把 master 分支合并到dev分支（仅一次）
	git merge master
3. 修改代码
4. 提交代码
	git add .
	git commit -m "xx"
	git push origin dev
```

回到家中继续写代码

```
1. 切换到 dev 分支进行开发
	 git checkout dev
2. 拉代码
	git pull origin dev
3. 继续开发
4. 提交代码
	git add .
	git commit -m "xx"
	git push origin dev
```

在公司继续开发

```
1. 切换到 dev 分支进行开发
	 git checkout dev
2. 拉代码
	git pull origin dev
3. 继续开发
4. 提交代码
	git add .
	git commit -m "xx"
	git push origin dev
```

开发完毕，要上线

```
1. 将 dev 分支合并到 master分支，进行上线
	git checkout master
	git merge dev
	git push origin master
2. 把 dev 分支也推送到远程仓库
	git checkout dev
	git merge master
	git push origin dev
```



## 第三章 其他

### 3.1 配置

* 项目配置文件：项目/.git/config

```
git config --local user.name "Ydk"
git config --local user.emial "11"
```

* 全局配置文件：~/.gitconfig

```
git config --global user.name "Ydk"
git config --global user.emial "11"
```

* 系统配置文件：/etc/.gitconfig

```
git config --system user.name "Ydk"
git config --system user.emial "11"

注意：需要有root权限
```



3.2 免密登录