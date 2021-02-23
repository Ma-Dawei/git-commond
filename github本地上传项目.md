## github本地上传项目



### 1.在2020年10月1起，github默认主分支从master更名为main，以上提交方式会默认创建一个master分支，为保持一致性，可将本地git init的时候默认分支修改为main，执行：

1. git --version    查看版本
2. git config --global init.defaultBranch main   git在2.28.0上，重新设置git默认分支为main

**Github账号创建和秘钥生成**

1.在github上创建（sign up）账号，https://github.com/join。填写邮箱，账号，验证.....

2.下载git安装。https://gitforwindows.org/

3.任何界面鼠标右键，选择git bash here。

4.配置全局账号和密码

```
git config --global user.name "name"



git config --global user.email "xxx@qq.com"
```

5.生成秘钥ssh-keygen -t rsa -C "你的公司或个人邮箱"

```
ssh-keygen -t rsa -C "xxx@qq.com"
```

执行命令，会弹出设置秘钥等，不想设置，直接enter，我是直接enter，3连刷。。。

6.查看生成秘钥位置

```python
cd ~/.ssh/      //切换到本电脑的.ssh文件夹
pwd               //当前目录
```

7.去上述目录下可以看到。
![img](https://img-blog.csdnimg.cn/20201019114028796.png)

8.打开公钥，复制粘贴到Github网站上的ssh_key上。

9.后续执行git clone github上的项目的sshkey地址，根据提示输入密码等，就可以下载项目。

**1.创建仓库**

1.1 创建仓库

![img](https://img-blog.csdnimg.cn/20201019114720473.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hhY2hpX3J0,size_16,color_FFFFFF,t_70)

![img](https://img-blog.csdnimg.cn/20201019114826216.png?x-oss-process=image/watermark,type_ZmFuZ3poZW5naGVpdGk,shadow_10,text_aHR0cHM6Ly9ibG9nLmNzZG4ubmV0L2hhY2hpX3J0,size_16,color_FFFFFF,t_70)

1.2 创建仓库后，点击clone，复制git地址

**2.本地代码上传到github**

2.1 在本地的项目工程目录下，安装shift，鼠标右键，git bash here，然后依次执行命令：

```
1.git init       //工作空间创建.git文件夹（默认隐藏了该文件夹）
2.git add .      //添加到暂存区
3.git commit -m "注释"
4.git remote add origin http://xxxxxxxxx.git   //本地仓库和远程github关联
5.git pull --rebase origin main    //远程有readme.md，拉一下
6.git push -u origin main        //代码合并
```