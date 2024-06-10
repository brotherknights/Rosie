# 第四阶段：Linux



## 第一节课：

### 1.github查询

awesome	去此标签中查询项目

tutorial		查资料、书籍、文档

...sample	查对应技术的代码样本



### 2.三要素：仓库 提交 分支

Respository 仓库：分为public和private的	是项目管理存储的基本单位

Commit		提交：在开发周期 有大量的对代码的迭代和修改都可以通过commit 来记录 便于回溯 和梳理开发流程、设计流程

Branch		分支：是代码的存储单元 默认的仓库主分支是master\main



### 3.仓库内容：code issues readme license

code：资源存储,代码，项目管理，许可证

issues：  问答->使用时遇到的bug提交回复

README：自述文件，开发进度，更新，介绍

LICENSE：许可证 GPL2.0 3.0 Apache 2.0 Mit 都是最大的权限，最小的限制



### 4.Git软件：分布式版本控制系统

仓库管理软件 

本地内容->发布内容



## 第二节课

### 1.git config -- list 查看git的配置文件

可以用来看有没有录入邮箱账号



### 2.创建本地仓库 git init

可以先在桌面创建一个文件夹的快捷方式 文件夹放在别的盘 然后 git init



### 3.实现登录和账号名录入

```
git config -- global user.email "  "

键值对 ->实现账号的登录 引号里填邮箱

git config -- global user.name "  "

->实现账号的登录 引号里填账号名
```



### 4.SSH远程访问



#### 4.1 创建本地密文：

```
SSH -- keygen -t rsa -C "邮箱"
```

创建成功会返回一个创建的本地地址：

1. 找到密文文件

2. 复制密文

3. 网站 new一个settings SSH ADD

   

#### 4.2 测试关联有无成功

```
ssh -T git@github.com
```



#### 4.3 为ssh仓库地址创建别名

```
git remote add origin "   "
```

origin就是仓库地址名字

remote可以改成remove 就是删除  



#### 5.git和github的交互逻辑

1. 文件：code.c

2. `git add code.c` 将文件上传到git里的缓冲区

3. `git commit "提交说明"` 将缓冲区里的文件上传到本地仓库

4. `git push origin master` 如果上传本地分支与云端的一致 那就会合并分支 

5. 到达云端仓库

   

#### 6.一些语句

查看状态:

`git status`



复位误删除的本地文件：从本地仓库下载下来 前提是本地仓库有

`git restore` 



删除本地文件+本地仓库文件

`git rm`



#### 7. 代码更新的依赖关系被破坏

直接修改云端内容 导致本地内容无法再提交 

解决方法：先拉取云端内容 与本地内容合并 再上传

`git pull -- rebase origin master`



#### 8.下载源代码

`git clone "网址"`



