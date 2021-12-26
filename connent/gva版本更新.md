

大家好，我是坚果，今天给大家介绍一个开源项目GIN-VUE-ADMIN，大家如果喜欢可以去github或者项目主页了解更多细节。

## 项目介绍

GIN-VUE-ADMIN是一个基于vue和gin开发的全栈前后端分离的开发基础平台，拥有jwt鉴权，动态路由，动态菜单，casbin鉴权，表单生成器，代码生成器等功能，提供了多种示例文件，让大家把更多时间专注在业务开发上。

## 缘起

在平时的开发工作中，无论做什么项目，都需要搭建一套开发基础平台，其中鉴权，动态路由，角色等等功能都是大同小异的，并且有大量的重复curd代码，因此下定决心，搞出了现在的gin-vue-admin

## 联系我们[#](https://www.gin-vue-admin.com/docs/#联系我们)

qq群：650421081([gin-vue-admin交流群](https://jq.qq.com/?_wv=1027&k=5cRp2f1R))

微信：`shouzi_1994` (备注 gin-vue-admin交流群) 通过验证后会拉你进微信群

## 在线体验[#](https://www.gin-vue-admin.com/docs/experience#在线体验)

[在线体验](http://demo.gin-vue-admin.com/) : [http://demo.gin-vue-admin.com](http://demo.gin-vue-admin.com/)

- 账号：admin 密码：123456
- 若环境崩溃请联系微信：shouzi_1994 或 清空缓存 等待5分钟,服务器会自动重置数据库数据
- 在线体验的配置管理功能, 配置文件可前台修改 无法体验,需要自行下载项目并运行进行体验

## 视频教程[#](https://www.gin-vue-admin.com/docs/base#视频教程)

- [【gin-vue-admin】从部署到发布：手把手带你使用GIN-VUE-ADMIN《2.3.5版本》（1010工作室出品）](https://www.bilibili.com/video/BV1fV411y7dT)
- [【gin-vue-admin】11/28更新：工作流介绍以及简单使用教学（1010工作室出品）](https://www.bilibili.com/video/BV1Ka411F7Ji)



##  项目架构

### 系统架构图

![系统架构图](https://luckly007.oss-cn-beijing.aliyuncs.com/images/gin-vue-admin.png)

### 前端详细设计图 （提供者:[baobeisuper](https://gitee.com/link?target=https%3A%2F%2Fgithub.com%2Fbaobeisuper)）

![前端详细设计图](https://luckly007.oss-cn-beijing.aliyuncs.com/images/naotu.png)

### 目录结构

```
    ├── server
        ├── api             (api层)
        │   └── v1          (v1版本接口)
        ├── config          (配置包)
        ├── core            (核心文件)
        ├── docs            (swagger文档目录)
        ├── global          (全局对象)                    
        ├── initialize      (初始化)                        
        │   └── internal    (初始化内部函数)                            
        ├── middleware      (中间件层)                        
        ├── model           (模型层)                    
        │   ├── request     (入参结构体)                        
        │   └── response    (出参结构体)                            
        ├── packfile        (静态文件打包)                        
        ├── resource        (静态资源文件夹)                        
        │   ├── excel       (excel导入导出默认路径)                        
        │   ├── page        (表单生成器)                        
        │   └── template    (模板)                            
        ├── router          (路由层)                    
        ├── service         (service层)                    
        ├── source          (source层)                    
        └── utils           (工具包)                    
            ├── timer       (定时器接口封装)                        
            └── upload      (oss接口封装)                        
    
    └─web            （前端文件）
        ├─public        （发布模板）
        └─src           （源码包）
            ├─api       （向后台发送ajax的封装层）
            ├─assets	（静态文件）
            ├─components（组件）
            ├─router	（前端路由）
            ├─store     （vuex 状态管理仓）
            ├─style     （通用样式文件）
            ├─utils     （前端工具库）
            └─view      （前端页面）
```

![前端详细设计图](https://www.gin-vue-admin.com/assets/images/naotu-6a2221047c930f3725e4af8fd814d7a7.png)

## 下载地址

https://github.com/flipped-aurora/gin-vue-admin

https://gitee.com/pixelmax/gin-vue-admin

联系方式

### 技术群

### QQ交流群：622360840

| QQ 群                                                        |
| ------------------------------------------------------------ |
| ![img](https://luckly007.oss-cn-beijing.aliyuncs.com/images/qq.jpg) |

### 微信交流群

| 微信                                                         |
| ------------------------------------------------------------ |
| ![img](https://luckly007.oss-cn-beijing.aliyuncs.com/images/qrjjz.png) |

添加微信，备注"加入gin-vue-admin交流群"

## 2021/12/25版本

### 版本号：2.4.6

### 功能：

- 1.增加了pgsql数据库初始化，用户可选用pgsql进行开发。
- 2.增加了业务数据库功能，用户可通过yaml中配置自己的业务数据库，根据name获取业务库进行业务操作，实现框架和业务的数据库分离。
- 3.oss集成了华为云oss。
- 4.前端打包增加了提示内存不足时的一键node内存扩容build命令。
- 5.调整了获取用户信息的方法，增加了不鉴权模式下的用户信息获取方式。
- 6.配置页面调整。
- 7.取消了自动化代码中数据库类型和size的选择模块，防止自动化代码报错。
- 8.前端element版本调整为1.2.0 beta.6 （所有icon可能需要进入菜单重新配置和进行代码调整）。

### 环境调整：

- 1.node版本需 ≥ 14。
- 2.go版本建议 ≥ 1.16。
- 3.vite版本锁定为 2.5.10。
- 4.vue版本锁定为 ^3.2.25。

### bug修复：

- 1.清理了package中的无用包。
- 2.修复了当存在同名文件时，自动化代码会覆盖同名文件导致项目无法使用 bug。
- 3.修复了gin代理前端页面时，静态文件错误的bug。
- 4.验证码验证规则将有后端获取数据，不再出现前后端配置不一致的情况。
- 5.修复了自动化代码中多个字段配置同一字典导致字典重复创建的bug。
- 6.修复了api管理页面批量删除无法生效的bug。
- 7.修复了api管理员面排序的sql注入漏洞。

### 其他调整：

- 1.增加了关键字等信息提升gva权重。
- 2.调整了一些业务细节，提升系统运行效率。
- 3.删除了一些无用文件。

