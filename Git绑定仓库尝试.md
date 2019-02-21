​	**2019年2月20日，学习Flutter的第三天，尝试用Git绑定仓库，实现从本地仓库到网端仓库的命令指示和文件传输。**

### 1、绑定我的账户并配置公钥

<u>1.1、绑定我的git账户</u>

​	右键桌面打开Git Bash，输入以下命令​	

```
$ git config --global user.newkbb"
$ git config --global user.email "18112345678@163.com"
```

<u>1.2、设置SSH KEY（我的密钥）</u>

​	因为是没有绑定过的用户，也就没有密钥，所以先生成：

```
$ ssh-keygen -t rsa -C "18112345678@163.com"
```

​	**注意：-C后面有个空格，空格后才是邮箱。**

​	生成过程回车3次就好，默认路径，默认无密码登录。

​	生成成功后，在对应目录C:\Users\Administrator.ssh里（Administrator是电脑用户名）用记事本打开id_rsa.pub，即SSH KEY公钥。

<u>1.3、在GitHub中配置我的SSH KEY</u>

​	打开Settings→SSH菜单→Add新增密钥→将本地的公钥粘贴→生成密钥

### 2、上传本地文件到GitHub

2.1、 建立本地仓库text​	

​	首先进入创建好的text仓库文件夹，这里我是在F盘建立的。

```
$ cd f:text
```

​	接着执行git初始化指令：

```
$ git init
```

​	执行指令将所有文件添加到仓库，这里我的text文件夹中只有一个昨天编写的HelloWorld.md程序。

```
$ git add
```

​	执行指令，提交文件（双引号内是注释）：

```
$ git commit -m "提交HelloWorld"
```

2.2、 关联GitHub仓库

​	首先去GitHub text仓库复制仓库地址，这里我的地址是https://github.com/newkbb/FirstGit-repoHelloWorld.git

​	执行指令：

```
$ git remote add origin https://github.com/newkbb/FirstGit-repoHelloWorld.git
```

​	上传本地代码：

```
$ git push -u origin master
```

​	然后F5一下GitHub，完成第一次本地仓库提交啦！！

