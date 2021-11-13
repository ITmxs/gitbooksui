# Hexo部署出现错误 Error: Spawn failed 解决方式

> Hexo部署出现一下错误err: Error: Spawn failed解决方式

```none
FATAL {
  err: Error: Spawn failed
      at ChildProcess.<anonymous> (C:\Users\myosotis\Desktop\Hexo_blog\node_modules\hexo-util\lib\spawn.js:51:21)
      at ChildProcess.emit (events.js:315:20)
      at ChildProcess.cp.emit (C:\Users\myosotis\Desktop\Hexo_blog\node_modules\cross-spawn\lib\enoent.js:34:29)
      at Process.ChildProcess._handle.onexit (internal/child_process.js:277:12) {
    code: 128
  }
} Something's wrong. Maybe you can find the solution here: %s https://hexo.io/docs/troubleshooting.html
```





### 方法一

```bash
##进入站点根目录

##删除git提交内容文件夹
rm -rf .deploy_git/

##执行
git config --global core.autocrlf false

##最后
hexo clean && hexo g && hexo deploy
```



### 方法二

> 修改 _config.yml 文件，将配置地址http方式切换成ssh方式

```bash
##进入站点根目录

##删除git提交内容文件夹
vim _config.yml

##修改
deploy:

type: git

repository: https://github.com/Uninfo/blog.github.io.git 
-> git@github.com:Uninfo/blog.github.io.git

branch: master

##最后
hexo clean && hexo g && hexo d
```



### 方法三

> 强制上传，不建议

```bash
##进入站点根目录

##进入depoly文件夹
cd .deploy_git/

##强制推送
git push -f
```