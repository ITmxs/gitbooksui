使用Typecho框架一个月又十二天了，就目前感受来讲，总体还不错，不少方面都支持个性化，二次开发，可是目前MD编辑器有一丢丢问题，不能同步滚动条滚动，就是编辑器区域滚动，预览区域没有动静，须要两边都操做，不知道这个问题是主题的仍是官方的，并且还有一个图片多了会出现抖动。。。html

其余的还好吧，插件也是蛮多的，那么开始吧，此教程使用本地虚拟机建立的CentOs7服务器。git

跟阿里云，腾讯云等等CentOs服务器是同样的，只是在本地演示一下，若是没有服务器的安装一个本地虚拟机服务器爽爽也ok啊，本地虚拟机服务器安装我也有写（[点击跳转到本地虚拟机安装CentOs7服务器](https://blog.langting.top/archives/117.html)）。github



Typecho 是国内开发者开发的一款开源免费的动态博客程序，可以运行在基于 PHP 环境的各种平台上。

- 官网：[Typecho Official Site](https://link.zhihu.com/?target=http%3A//typecho.org/)
- GitHub：[typecho: A PHP Blogging Platform.](https://link.zhihu.com/?target=https%3A//github.com/typecho/typecho)

相比于同为动态博客并且广为人知的 WordPress 来说，Typecho 的一大特点就是 “精简”。全部文件不足 500KB，但却也实现了完整的主题和插件支持。博客程序很轻量，资源占用也很低，原生支持 Markdown 语法。属于省心并且简洁的博客类型。



## 下载Typecho安装包

- Typecho官网：[typecho.org/](http://typecho.org/)

点击`当即下载`。 shell

![1.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/9070d410dd9c4985bff92814feea65db-1.jpg)



点击`下载正式版`。 数据库

![image-20211111111754094](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111111754094.png)



下载完成后会获得一个.gz后缀的文件（Linux和macOS下的压缩格式），windows下解压（我这里用的解压软件是7z：[www.7-zip.org/）两次就能够获得](https://www.7-zip.org/）两次就可以得到)`build`文件夹。 windows

![3.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/fdfb7aa20367446c85c639a87d08dfab-1.jpg)



进入build文件夹里面，将全部文件压缩，这是为了方便上传到宝塔。 服务器

![4.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/79f308f8696a41bf92ca3fca20726b44-1.jpg)



## 宝塔面板配置

宝塔面板`建立网站`。 框架

![5.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/ec451f1f8d9241d7b22d345de35de634-1.jpg)



本地`hosts`文件（`C:\Windows\System32\drivers\etc`）配置一下访问域名。 编辑器

![6.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/0cd5a69633454a4ca0caf65780df19ea-2.png)



访问域名：`blog.langting.io`，出现下图内容就说明建立网站成功了。 typecho

![7.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/c09422aa1b7b4ab890aa47ab7c8ce915-1.jpg)



而后回到宝塔面板，`文件`->`blog.langting.io`文件夹里，删除全部文件（删除后若是还有`.user.ini`文件，继续删除他）。

![8.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/9622d453f9254f35abe0f082bf679283-1.jpg)



上传以前已打包的压缩包`build.zip`。

![9.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/0e43799be4cd47f89f61ad50276e70c8-1.jpg)



解压`build.zip`。

![10.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/e93191a6c89b47e58654c1a2b759b202-1.jpg)



解压到当前了，删掉`build.zip`，你要留着也行。

![11.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/3602e68cc5df4b459cce35183ba582e1-1.jpg)



**别忘了文件权限问题，在Xshell里或者宝塔面板也有一个终端，进入cd /www/wwwroot**，好像在宝塔面板也能够改文件权限，本身研究一下。 chown -R www.www 文件名 chmod -R 750 文件名

再次打开域名：`blog.langting.io`，Typecho框架完好无损（能够打开F12看看有没有报错，个人没有）。

![12.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/62162d3e98b843eaa459cd7236bd90cc-1.jpg)



## 安装Typecho

点击`我准备好了, 开始下一步 »`。

![13.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/cb4afbbbf17d40afb7e1077713ec0723-1.jpg)



配置Typecho信息。

![14.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/98f1418668b6462a85406344e1be1235-1.jpg)





![15.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/51a13c81cd5740d783795800a1d53f5f-1.jpg)



数据库信息。

![17.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/ecf9e0b8198b468f9c70092470891f39-1.jpg)



看到下图就说明安装成功了，恭喜恭喜。

![16.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/b99809d784a2493f8e421d20e2020343-1.jpg)



打开域名：`blog.langting.io`，展现前台（用户/游客看到的界面）。

![18.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/72fdff4f423c4b8dbcf1829a25917797-1.jpg)



打开域名：`blog.langting.io/admin`，展现后台（本身看到的界面，记得密码别泄露）。

![19.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/40f7a59e3c4f49e38ea3420fc1c09e8b-1.jpg)





![20.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/a19804f5122b4591a4c11eb5c94de21b-1.jpg)



## 静态化配置：

配置静态化，先设置网站伪静态。

![21.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/2d92b3d196cb495e911327317159dde1-1.jpg)



配置静态化，再设置网站连接模式（**若是提示报错，就按照提示操做，这里我忘记截图了**）。

![22.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/0a6663628c414891bba3ced3c5c72b14-1.jpg)



## 插件

Typecho 主题模板站

https://typecho.me/

**全部的主题和插件管理都在这里**

![23.png](https://luckly007.oss-cn-beijing.aliyuncs.com/image/ded84e0ff7a940bd8d4323c214bc46b1-1.jpg)



本站用到的插件以下（安装就不说了，每个插件都有教程的）：

- 主题：[aria-doc.eriri.ink/#/](https://aria-doc.eriri.ink/#/)
- 炫彩鼠标：[www.hoehub.com/PHP/typecho…](https://www.hoehub.com/PHP/typecho-HoerMouse.html)
- 疯狂打字机：[www.hoehub.com/PHP/typecho…](https://www.hoehub.com/PHP/typecho-ActivatePowerMode.html)
- 访问统计：[kotori.love/archives/ty…](https://kotori.love/archives/typecho-plugin-access.html)
- 播放在线音乐：[github.com/MoePlayer/A…](https://github.com/MoePlayer/APlayer-Typecho)
- 在底部显示系统的运行时长：[github.com/zhusaidong/…](https://github.com/zhusaidong/SiteRunningTime)
- 网站地图：[github.com/bayunjiang/…](https://github.com/bayunjiang/typecho-sitemap)

正式上线的博客搭好后，别忘了加我一条友链哦！



## 参考文章

https://www.google.com.hk/search?q=windows+%E5%AE%89%E8%A3%85typecho&oq=windows+%E5%AE%89%E8%A3%85typecho&aqs=chrome..69i57.13469j0j4&sourceid=chrome&ie=UTF-8



https://zhuanlan.zhihu.com/p/34211709

https://boke112.com/post/7394.html



![image-20211111112530129](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111112530129.png)





设置1212端口



## 宝塔面板

安装命令

```
yum install -y wget && wget -O install.sh http://download.bt.cn/install/install_6.0.sh && sh install.sh
```



之后会问你是否确认下载，选择“y”。

等待3分钟左右，面板安装成功，显示信息包括后台地址、账户和密码。

![image-20211111130111941](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111130111941.png)



查看8888端口



```
 firewall-cmd --list-ports --permanent

```

进入后台http://121.199.29.213:8888/c73c5d58/

输入账户和密码，即可登录宝塔后台。







阿里云管理面板

![image-20211111131254386](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111131254386.png)



Xjg201314



防火请参考文章

https://blog.csdn.net/qq_39132095/article/details/120487721?spm=1001.2014.3001.5502



关于宝塔的一些命令



输入bt

```
bt
```

![image-20211111131810909](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111131810909.png)



改用户名

![image-20211111132230370](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111132230370.png)

改密码

![image-20211111132305076](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111132305076.png)

### 登录http://121.199.29.213:8888/c73c5d58/

![image-20211111132333853](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111132333853.png)



统一条款

![image-20211111132416251](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111132416251.png)

安装



![image-20211111132618671](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111132618671.png)





这块重点

![image-20211111133008941](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111133008941.png)





![image-20211111133517608](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111133517608.png)





![image-20211111134810464](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111134810464.png)

![image-20211111135218056](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111135218056.png)

![image-20211111135237002](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111135237002.png)





![image-20211111135401608](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111135401608.png)



EZnjTrjTh3p8edy6

![image-20211111140811194](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111140811194.png)

![image-20211111135643066](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111135643066.png)



执行下面命令查看，面板数据库没有用systemctl进行管理的

1. /etc/init.d/mysqld status





![image-20211111140428422](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111140428422.png)





![image-20211111140519891](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111140519891.png)





![image-20211111140635949](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111140635949.png)



访问

http://121.199.29.213/install.php



![image-20211111141059372](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111141059372.png)

![image-20211111141201674](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211111141201674.png)





访问博客

http://121.199.29.213/index.php



控制面板

http://121.199.29.213/admin/welcome.php



## 配置主题





下载喜欢的目录，放到user theme



主题启用



文件夹上传图片当作背景

或者自己的图床文件都可以