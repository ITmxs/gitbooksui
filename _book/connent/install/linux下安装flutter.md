# linux 环境安装Flutter

### 手动安装 Flutter

如果你没有 `snapd`，或者你无法使用它，那么你可以通过以下步骤安装 Flutter。

1. 通过下载下面的安装包以获得最新 stable release 版本的 Flutter SDK：

   [flutter_linux_2.5.2-stable.tar.xz](https://storage.flutter-io.cn/flutter_infra_release/releases/stable/linux/flutter_linux_2.5.2-stable.tar.xz)

   对于其他发布频道以及更久的构建版本，请查看 [SDK 发布](https://flutter.cn/docs/development/tools/sdk/releases) 页面。

2. 将文件解压到合适的地方，例如：

   ```
   $ cd ~/development
   $ tar xf ~/Downloads/flutter_linux_2.5.2-stable.tar.xz
   ```

   如果你不想安装安装包的补丁，你可以跳过步骤 1 或步骤 2，直接获取 Github 上 [Flutter 仓库](https://github.com/flutter/flutter) 的源码并执行以下命令：

   ```
   $ git clone https://github.com/flutter/flutter.git
   ```

   



![image-20211008151946566](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211008151946566.png)



```
export PATH="$PATH:`pwd`/flutter/bin"

```

你也可以按你的需要切换分支或者tag。例如，你可以使用 stable 版本的分支：



```
$ git clone https://github.com/flutter/flutter.git -b stable
```

将 `flutter` 工具添加到环境变量中：

```
$ export PATH="$PATH:`pwd`/flutter/bin"
```

用这个命令添加 `PATH` 仅在当前的命令行视窗生效。要将 Flutter 永久添加到环境变量中，请参阅 [更新您的路径](https://flutter.cn/docs/get-started/install/linux#update-your-path)。

![image-20211008153633482](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211008153633482.png)

可选步骤，提前下载二进制开发文件：

`flutter` 工具将下载所需的平台特殊开发二进制文件。对于预下载这些工件更好的做法是（例如，在系统构建环境中，网络可能出现不通畅的问题），通过运行下面命令提前下载 iOS 和 Android 的二进制文件：

```
$ flutter precache
```

对于这些可选的下载项，请参考 `flutter help precache`。

你现在可以运行 Flutter 命令了！

 **提示**

要更新已有 Flutter版本，请参阅[升级你的 Flutter](https://flutter.cn/docs/development/tools/sdk/upgrading)。

### 运行 flutter doctor

运行以下命令以查看是否还有缺失的依赖需要安装，你需要安装这些依赖以完成设置（要看到详细输出，请添加 `-v` 标识）：

```
$ flutter doctor
```

![image-20211008154213986](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211008154213986.png)