[Github Actions](https://link.zhihu.com/?target=https%3A//github.com/features/actions) 是 GitHub 官方 CI 工具，与 GitHub 无缝集成。之前博客使用 TravisCI 实现的自动部署，现在转用 GitHub Actions 部署，本文记录部署流程。


简单介绍下 GitHub Actions 中的术语：

- workflow：表示一次持续集成的过程
- job：构建任务，一个 workflow 可以由一个或者多个 job 组成，可支持并发执行 job
- step：一个 job 由一个或多个 step 组成，按顺序依次执行
- action：每个 step 由一个或多个 action 组成，按顺序依次执行

------

接下来介绍下操作步骤：

## 1.博客工程

GitHub 博客创建步骤非本文重点，请自行搜索。
推荐使用 `master` 分支作为最终部署分支，源码分支可以根据自己喜好创建，我这里创建的是 `hexo`。

## 2.生成公私钥

```
ssh-keygen -t rsa -b 4096 -C "Hexo Deploy Key" -f github-deploy-key -N ""
```

![image-20211113084619620](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113084619620.png)

## 3.GitHub 配置秘钥

我们把`私钥`放到我们存放 Hexo 原始文件的代码仓库里面，用于触发 Actions 时使用。

把`公钥`放到 GitHub Pages 对应的代码仓库里面，用于 Hexo 部署时的写入工作。

### 3.1.配置私钥

我们把`私钥`放到我们存放 Hexo 原始文件的代码仓库里面，用于触发 Actions 时使用。

![image-20211113085050861](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113085050861.png)

首先在 GitHub 上打开保存 Hexo 的仓库，访问 `Settings -> Secrets`，画面如下：

在 GitHub 中博客工程中按照 `Settings->Secrets->Add a new secrets` 找到对应的页面，然后进行私钥添加。该页面中 `Name` 自定义即可，`Value` 中添加 `github-deploy-key` 文件中的内容。

然后选择 `New secret`



名字部分填写：`HEXO_DEPLOY_KEY1`，注意大小写，这个后面的 GitHub Actions Workflow 要用到，一定不能写错。

在 `Value` 的部分填入 `github-deploy-key` 中的内容：

![image-20211113085809121](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113085809121.png)

添加了私钥以后的界面显示如下：

### 3.2GitHub 添加公钥

把`公钥`放到 GitHub Pages 对应的代码仓库里面，用于 Hexo 部署时的写入工作。

在 GitHub 中博客工程中按照 `Settings->Deploye keys->Add deploy key` 找到对应的页面，然后进行公钥添加。该页面中 `Title` 自定义即可，`Key` 中添加 `github-deploy-key.pub` 文件中的内容。

按 `Add deploy key` 来添加一个新的公钥：

![image-20211113085551610](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113085551610.png)

![image-20211113085609696](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113085609696.png)

## 4.创建编译脚本

在博客源码分支(我这里是hexo分支)中创建 `.github/workflows/HexoCI.yml` 文件，内容如下：

在 `Title` 中输入：`HEXO_DEPLOY_PUB` 字样，当然也可以填写其它自定义的名字。

在 `Key` 中粘贴 `github-deploy-key.pub` 文件的内容。

> 注意：一定要勾选 `Allow write access` 来打开写权限，否则无法写入会导致部署失败。

最后添加好了公钥的界面如下：



## 创建 Workflow

首先在 Hexo 的仓库中创建一个新文件：`.github/workflows/deploy.yml`，文件名可以自己取，但是一定要放在 `.github/workflows` 目录中，文件的内容如下：





```yaml
name: Hexo Deploy

on:
  push:
    branches:
      - master

jobs:
  build:
    runs-on: ubuntu-18.04
    if: github.event.repository.owner.id == github.event.sender.id

    steps:
      - name: Checkout source
        uses: actions/checkout@v2
        with:
          ref: master

      - name: Setup Node.js
        uses: actions/setup-node@v1
        with:
          node-version: '12'

      - name: Setup Hexo
        env:
          ACTION_DEPLOY_KEY: ${{ secrets.HEXO_DEPLOY_KEY }}
        run: |
          mkdir -p ~/.ssh/
          echo "$ACTION_DEPLOY_KEY" > ~/.ssh/id_rsa
          chmod 700 ~/.ssh
          chmod 600 ~/.ssh/id_rsa
          ssh-keyscan github.com >> ~/.ssh/known_hosts
          git config --global user.email "john@doe.com"
          git config --global user.name "John Doe"
          npm install hexo-cli -g
          npm install

      - name: Deploy
        run: |
          hexo clean
          hexo deploy
```

简单解释一下，当我们推送内容到远程 `master` 分支的时候，就会触发这个 Workflow。

使用 `Ubuntu 18.04` 作为 `hexo deploy` 的系统。

首先 checkout 源代码，然后设置使用最新的 Node.js v12 LTS 作为 node 解释器。

接下来就是创建 SSH 相关的配置文件，注意 `secrets.HEXO_DEPLOY_KEY` 就是对应我们之前设置的私钥，所以名字一定不要搞错。

`git config` 相关的名字和邮件地址替换成大家自己使用的就好了。

最后就是安装 Hexo CLI，各个依赖模块和部署了。



## 验证

下面就是 GitHub Actions 页面显示的运行结果：



前面有绿色钩钩的，就表示部署成功，红色叉叉的表示失败。如果部署失败，还会收到 GitHub 的邮件提醒。

好了，以上就是利用 GitHub Actions 自动部署 Hexo 到 GitHub Pages 的方法，谢谢观赏。