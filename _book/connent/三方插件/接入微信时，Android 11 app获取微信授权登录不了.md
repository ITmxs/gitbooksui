# Android 11 app获取微信授权登录不了

```
IWXAPI.isWXAppInstalled() 提示微信未安装， 授权登录Android11没响应，无法跳到 WXEntryActivity 页面。
sendReq failed for wechat app signature check. failed
```

利用签名工具，发现签名是 正确的，

解决方案：

### Android 11 系统策略更新，请开发者及时适配

Android 11 版本为加强用户隐私保护引入较多变更，第三方应用需要适配的有两个变更：

1.软件包可见性变更，会导致第三方应用通过 OpenSDK 接口拉起微信受限，从而影响分享消息到微信、拉起小程序等功能的正常使用（该变更只对升级targetSdkVersion=30 的应用产生影响）。

2.[强制执行分区存储](https://developer.android.com/about/versions/11/privacy/storage#scoped-storage)：该变更会影响第三方应用分享包含文件路径的消息（如图片类型消息），无论第三方应用targetSdkVersion是否升级为30，均需要进行适配。

为避免未及时适配带来的使用问题，请开发者尽快适配。

### 1. 软件可见性适配方案

1.1 根据 Android 官方给出的适配方案，在主工程的AndroidManifest.xml 中增加 标签，即可解决以上影响，代码如下：

```
<manifest package="com.example.app">

      ...

      // 在应用的AndroidManifest.xml添加如下<queries>标签
    <queries>
        <package android:name="com.tencent.mm" />   // 指定微信包名
    </queries>

      ...

</manifest>
```

如果是flutter项目。该路径为：![image-20210409095921523](https://gitee.com/itmxs/images/raw/master/img/image-20210409095921523.png)



1.2 添加以上标签之后，需要开发者升级编译工具，否则会出现编译错误。

1）Android Studio 需要升级至 3.3 及以上，建议升级至 4.0 及以上版本；我的版本4.1.2

2）Android SDK Build-Tools 需要升级至 30 及以上版本；我的30

3）com.android.tools.build:gradle 需要升级至 3.6.0 版本，建议升级至最新的 3.6.4 版本。我的3.6.4

### 2. 分区存储适配

针对 Android 11 及以上系统，如果分享的消息中涉及文件路径（如图片类型消息），无论应用的targetSdkVersion是否为30，均需使用 FileProvider 的方式进行分享，否则将出现由于分享的文件路径异常导致的分享失败。详情查阅[《OpenSDK 支持 FileProvider 方式分享文件到微信文档》](https://developers.weixin.qq.com/community/develop/doc/0004886026c1a8402d2a040ee5b401)。

了解更多可查看 [Android接入指南](https://developers.weixin.qq.com/doc/oplatform/Mobile_App/Access_Guide/Android.html)。