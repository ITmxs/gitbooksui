# 快速上手

<details style="color: rgb(44, 62, 80); font-family: -apple-system, BlinkMacSystemFont, &quot;Segoe UI&quot;, Roboto, Oxygen, Ubuntu, Cantarell, &quot;Fira Sans&quot;, &quot;Droid Sans&quot;, &quot;Helvetica Neue&quot;, sans-serif; font-size: 16px; font-style: normal; font-variant-ligatures: normal; font-variant-caps: normal; font-weight: 400; letter-spacing: normal; orphans: 2; text-align: start; text-indent: 0px; text-transform: none; white-space: normal; widows: 2; word-spacing: 0px; -webkit-text-stroke-width: 0px; background-color: rgb(255, 255, 255); text-decoration-thickness: initial; text-decoration-style: initial; text-decoration-color: initial;"><summary>开始之前，鄙人希望您能认识到以下几点【点击展开】</summary></details>

## [#](https://hexoplusplus.js.org/start/#部署代码)部署代码

先下载，你可以直接从[Github (opens new window)](https://raw.githubusercontent.com/HexoPlusPlus/HexoPlusPlus/main/index.js)上下载，也可以用[JSdelivr (opens new window)](https://cdn.jsdelivr.net/gh/HexoPlusPlus/HexoPlusPlus@main/index.js)加速下载，复制里面的内容。

进入[CloudFlare (opens new window)](https://cloudflare.com/),注册账户，开通workers不再阐述。

点击KV选项，进入并创建一个KV桶，命名空间名称随意

![image-20211113094700540](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113094700540.png)

![image-20211113095036705](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113095036705.png)

### 配置账户

返回，先配置变量，`hpp_username`和`hpp_password`，这将分别为你的登录用户名和密码.

以及一个`hpp_captcha`,`False`为关闭，`True`为开启验证码

> 强烈建议两者加密保护安全。

> 0.1.3版本及以上支持了多用户登录，多个用户名和密码请用英文符号`,`分割，并且一一对应

> 例如：

> hpp_username：A,B,C

> hpp_password：A'sPassword,B'sPassword,C'sPassword

![image-20211113095215791](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113095215791.png)

再划到底下-KV 命名空间绑定-编辑变量-新增变量绑定-变量名称：KVNAME【此处不可更改】，KV命名空间：您之前写的空间名字，如图所示



![image-20211113095301381](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113095301381.png)

绑定域名【可选】

![img](https://luckly007.oss-cn-beijing.aliyuncs.com/img/11.png)

> 此处域名后面必须加`/*`

> 如果你直接将HPP绑定在博客以下，并且您的博客是由CloudFlare作为CDN的，那么请将绑定路由设置为`yourdomain/hpp/*`

## [#](https://hexoplusplus.js.org/start/#安装)安装

## 安装

> **注意！** 并不是所有的安装项都要填。HexoPlusPlus安装时配置项较多，如果你实在不想填，可以留空，部分必填值会直接缺省。

直接进入域名会得到错误页面，请在后面加上`/hpp/admin/login`再登录。

![image-20211113095606729](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113095606729.png)

> **注意！** HexoPlusPlus默认以HTTPS格式传输，外部链接也必须以HTTPS，否则会加载失败

> `必填`指此键值必须要填写,若不填写可能会导致功能异常

### [#](https://hexoplusplus.js.org/start/#域名-必填)`域名` `必填`

指HexoPlusPlus绑定的域名，可以是上一步自定义的域名，也可以是CloudFlare分配的三级域名

![image-20211113095652690](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113095652690.png)

![image-20211113095833581](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113095833581.png)![image-20211113101550420](https://luckly007.oss-cn-beijing.aliyuncs.com/img/image-20211113101550420.png)