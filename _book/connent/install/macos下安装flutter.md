# macOS 环境安装Flutter

## macOS 的系统要求

要在 macOS 系统上安装和运行 Flutter，您首先需要满足您的开发环境的这些要求。

| **操作系统**     | macOS（64 位）                            |
| ---------------- | ----------------------------------------- |
| **磁盘空间**     | 2.8 GB（不包括用于 IDE/工具的磁盘空间）。 |
| **工具**         | bash curl git 2.x mkdir rm unzip which    |
| **集成开发环境** | Xcode（官方）                             |

## 获取 Flutter SDK

**步骤 1：**下载 macOS 的 Flutter 软件开发工具包的安装包。要下载 Flutter SDK，请访问其官方[网站](https://flutter.dev/docs/get-started/install/macos)。

**第 2 步：**下载完成后，解压缩 zip 文件并将其放置在所需的安装文件夹或位置。

将文件解压到目标路径, 比如:

```
$ cd ~/development
$ unzip ~/Downloads/flutter_macos_2.5.2-stable.zip
```

**第三步：**要运行Flutter命令，需要更新系统路径以包含flutter bin目录。

配置 `flutter` 的 PATH 环境变量：

```
$ export PATH="$PATH:`pwd`/flutter/bin"
```

**第 4 步：**接下来，使用以下命令在当前终端窗口中启用更新的路径，然后也进行验证。

```
source ~/.bashrc  
source $HOME/.bash_profile  
echo $PATH  
```

**第 5 步：**现在，运行 $ **flutter doctor**命令。此命令检查 Flutter 应用程序开发的所有要求，并显示 Flutter 安装状态报告。

```
$ flutter doctor  
```

**第六步：**当您运行上述命令时，它会分析系统和所有缺少的工具的详细信息，这些工具需要运行 Flutter 以及可用但未与设备连接的开发工具。

**步骤 7：**如果 Flutter doctor 工具报告，请安装最新的 Xcode 工具。

**第八步：**安装最新的Android Studio和SDK，如果Flutter Doctor工具报告了。

**步骤 9：**接下来，您需要设置一个 iOS 模拟器或将 iPhone 设备连接到系统以开发 iOS 应用程序。

**第 10 步：**再次设置 android 模拟器或将 android 设备连接到系统以开发 android 应用程序。

**第 11 步：**现在，安装 Flutter 和 Dart 插件以在 Android Studio 中构建 Flutter 应用程序。这些插件提供了创建 Flutter 应用程序的模板，提供了在 Android Studio 本身中运行和调试 Flutter 应用程序的选项。

