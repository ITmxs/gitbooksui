[TOC]

今天是Flutter系列第六节。今天给大家介绍flutter版本控制工具 `FVM` 

# FVM 切换VSCode 的Flutter版本

随着flutter2.5.0的发布，相信很多同学都是激动的心，颤动的手，想快速尝试一波，做一个吃螃蟹的人，本人也是曾怀揣着这样的心情，头脑一热的将本地的flutter版本更新到2.05.0了，螃蟹吃完了，但是回到项目（公司项目采用的1.20.4）代码时，一打开，一片红，各种报错，我滴个乖乖～，又赶紧将版本回退到之前的稳定版本！

本着又想吃螃蟹，又想兼顾公司项目代码的想法，还是幼稚了，幸运的是，**https://github.com/leoafarias/fvm** 就能满足需求。在这里介绍一款flutter的版本管理神器 `FVM`，安装方式我给了两种，

`choco`和`choco`

FVM 可以在用户本机通过安装多个Flutter SDK版本，来为项目指定Flutter版本，或者快速在各个版本间切换,解决只有一个Flutter版本对不同项目兼容问题。

##  在windows上安装fvm

###  方法一：先安装  choco

官网：

https://chocolatey.org/

powershell 管理员身份运行命令行

 不会的话，先打开一个powershell 窗口 ，然后右击任务栏，选择第一个，即可进入

![image-20211102144556391](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211102144556391.png)

输入命令

- cmd 安装
  直接拷贝执行即可，注意需要管理员身份运行

```
@"%SystemRoot%\System32\WindowsPowerShell\v1.0\powershell.exe" -NoProfile -InputFormat None -ExecutionPolicy Bypass -Command "iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))" && SET "PATH=%PATH%;%ALLUSERSPROFILE%\chocolatey\bin"
```

- PowerShell 安装

```
Set-ExecutionPolicy Bypass -Scope Process -Force; [System.Net.ServicePointManager]::SecurityProtocol = [System.Net.ServicePointManager]::SecurityProtocol -bor 3072; iex ((New-Object System.Net.WebClient).DownloadString('https://chocolatey.org/install.ps1'))
```

#### 检查安装是否成功

```undefined
choco -v
```

- 更新

```undefined
choco upgrade chocolatey
```

可以安装成功

## 常用指令

`choco list -li` 查看本地安装的软件

`choco search nodejs` 查找安装包

`choco install sublimetext3` 下载

`choco uninstall sublimetext3` 卸载

`choco upgrade sublimetext3` 更新（update）



![image-20211102144643292](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211102144643292.png)

## 接下来安装fvm

```
 choco install fvm
```



##  方法二：pub方式安装 fvm

```
pub global activate fvm
```



可以设置系统环境变量、

<h2 id="1">1.语法示例</h2>

![image-20211102170024588](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211102170024588.png)

###  VSCode配置

现在我们将在这里配置 VS Code，我们将看到如何完成 VS Code 过程。

目录的路径，我们可以在代码中看到 FVM 安装的所有版本

这里提示在settings.json添加以下内容。

```
{
  "dart.flutterSdkPaths": ["D:/fvm/versions""]
}
```

用fvm命令，输入`fvm`出现如下信息，即配置成功，可以开始使用fvm管理了。



![image-20211102142541128](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211102142541128.png)

为了获得上面的路径，我们将执行 fvm list 命令

```
// copy this path
Versions path:  $YOUR_PATH/fvm/versions
```

输入 cmd + shift + p 来使用 sdk，然后输入 change sdk，现在你可以选择你喜欢的版本了。

![image-20211102144908030](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211102144908030.png)

初始化项目

```
$ fvm flutter create .
```





### 安卓studio

1. 前往`Languages & Frameworks -> Flutter`或搜索 Flutter 并更改 Flutter SDK 路径。
2. 将fvm 符号链接的***绝对\***路径复制到您的项目根目录中。例子：`/absolute-path/.fvm/flutter_sdk`
3. 应用更改。
4. 重新启动 Android Studio 以查看应用的新设置。

您现在可以使用所选版本的 Flutter 运行和调试。



## Flutter版本切换

版本切换前先用`fvm list` 检查一下本地版本

```
Cache Directory:  D:\fvm\versions

2.5.1
2.5.0
2.2.3
1.20.4
```

![image-20211102143654846](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211102143654846.png)

然后使用`fvm list`切换你想要的版本

```
PS E:\work\dc-client\app_proj> fvm use 1.20.4
Project now uses Flutter [1.20.4]

```





![image-20211102142958930](https://luckly007.oss-cn-beijing.aliyuncs.com/image/image-20211102142958930.png)

其他的设置同电脑终端的设置一样，可以参考：[github.com/leoafarias/…](https://link.juejin.cn/?target=https%3A%2F%2Fgithub.com%2Fleoafarias%2Ffvm%23vscode)

## 项目

FVM 将在您的项目中创建一个相对符号链接`.fvm/flutter_sdk`到所选版本的缓存。将其添加到您的`.gitignore`

```
.fvm/flutter_sdk.gitignore

.fvm/flutter_sdk
```

### 缓存目录

您可以通过设置环境变量来配置**fvm**缓存目录`FVM_HOME`。如果没有设置，将使用默认的**fvm**路径。您还可以通过`--cache-path`在配置上设置来更改目录。见下文

#### 列出配置

```
fvm config
```

###  设置缓存路径

```
fvm config --cache-path <CACHE_PATH>
```



### 配置

您可以在 FVM 上更改一些配置。**在 CLI 上设置的所有设置都与 Sidekick(GUI) 兼容**。





## 常用命令

一般需要查看命令的使用说明，都会通过 `--help` 查看。

```
$ fvm --help
Flutter Version Management: A cli to manage Flutter SDK versions.

Usage: fvm <command> [arguments]

Global options:
-h, --help       Print this usage information.
    --verbose    Print verbose output.

Available commands:
  config     Set configuration for FVM
  flutter    Proxies Flutter Commands
  install    Installs Flutter SDK Version
  list       Lists installed Flutter SDK Version
  releases   Lists Flutter SDK releases.
  remove     Removes Flutter SDK Version
  use        Which Flutter SDK Version you would like to use
  version    Prints the currently-installed version of FVM

Run "fvm help <command>" for more information about a command.
```

- config：对 fvm 进行配置
- flutter：对 Flutter 的命令进行代理
- install：安装 Flutter 版本
- list：查看已安装的 Flutter 版本
- releases：查看 Flutter sdk 都有哪些发布的版本
- remove：删除已安装的某个 Flutter 的版本
- use: 选择你要使用的版本
- version: 查看安装 fvm 的版本

对于子命令的更多使用方法，我们可以通过  `fvm help <command>` 进行查看，比如：

```
$ fvm help use
Which Flutter SDK Version you would like to use

Usage: fvm use [arguments]
-h, --help      Print this usage information.
    --global    Sets version as the global version.
                Make sure Flutter PATH env is set to: /Users/oheroj/fvm/default/bin
    --force     Skips command guards that does Flutter project checks.

Run "fvm help" to see global options.
```

- -h，--help ：可以查看更多使用信息
- --global: 将这个版本设置为全局版本
- --force: 跳过执行 Flutter 项目检查命令

命令学习的套路就是多用 help。其他命令读大家可自行学习。





## 安装

安装 Flutter SDK 版本。使您能够安装 Flutter 版本或频道。

```dart
Usage:
    fvm install - # 安装在项目配置中找到的版本
    fvm install {version} - # 安装特定版本 
Option:
    -h, --help          Print this usage information.
    -s, --skip-setup    Skips Flutter setup after install
```

## 删除

删除 Flutter SDK 版本。将影响依赖于该版本 SDK 的任何项目。

```
Usage:
    fvm remove {version}

Option:
    -h, --help     Print this usage information.
        --force    Skips version global check.
```

## 列出

列出已安装的 Flutter SDK 版本。还将打印 FVM 使用的缓存目录。

```
Usage:
    fvm list

Option:
    -h, --help     Print this usage information.xxxxxxxxxx List#Usage:    fvm listOption:    -h, --help     Print this usage information.
```

## releases

查看所有可供安装的 Flutter SDK 版本。



```
Usage:
    fvm releases

Option:
    -h, --help     Print this usage information.
```



## doctor

显示有关环境和项目配置的信息。

```
Usage:
    fvm doctor

Option:
    -h, --help     Print this usage information.
```

### 路由

代理命令时，`FVM`将按以下顺序查找 sdk。

1. 项目
2. 父级 目录
3. 全局（通过 FVM 设置）
4. 环境（Flutter 版本配置于`PATH`）

# 配置全局版本

```
fvm global {version}
```

# 项目多个选项

您可以为每个项目环境或发布类型配置多个 Flutter SDK 版本。FVM 遵循 Flutter 的相同约定并将其称为`flavors`.

它允许您为您的项目创建以下配置。

```
{
  "flutterSdkVersion": "stable",
  "flavors": {
    "dev": "beta",
    "staging": "2.0.3",
    "production": "1.22.6"
  }
}
```



## 针对不用flavor版本

要为特定版本选择 Flutter SDK 版本，您只需使用该`use`命令。

```
fvm use {version} --flavor {flavor_name}
```

## 切换flavor版本

将获取为flavor配置的版本并设置为项目版本。

```
fvm flavor {flavor_name}
```



## 查看flavor

列出所有配置的口味：

```
fvm flavor
```





## 常见问题

### 运行 FVM 时内核二进制文件无效或 sdk 哈希无效

发生这种情况的原因有几个。但是这意味着 FVM 快照与安装的 Dart 版本不兼容。

请执行以下操作：

1. 在 Windows 上，请确保您的 env 变量按[PATH 中 Windows 的环境变量]顺序所述的顺序排列。
2. 跑 `dart pub global deactivate fvm`
3. 跑 `dart pub global activate fvm`

### PATH 中 Windows 的环境变量顺序

Flutter 内置了 Dart。因此，当单独运行 Dart 和 Flutter 时，您会发现一些冲突。这是我们发现的正确依赖顺序以避免出现问题的建议。

1. 全局包的发布缓存
2. Dart SDK（如果安装在 Flutter 之外）
3. 颤振SDK

它应该是这样的。

C:\Users\<用户>\AppData\Roaming\Pub\Cache\bin

C:\src\flutter\bin\cache\dart-sdk\bin

C:\src\flutter\bin

### 找不到命令“pub” 

如果您得到`Command 'pub' not found`，请确保附加`export PATH="$PATH:/usr/lib/dart/bin"`到您的`~/.bashrc`（每次打开 bash shell 时都会重新启动）或`~/.profile`（仅在登录时读取）文件。

`choco list -li` 查看本地安装的软件

`choco search nodejs` 查找安装包

`choco install sublimetext3` 下载

`choco uninstall sublimetext3` 卸载

`choco upgrade sublimetext3` 更新（update）



参考：

https://fvm.app/docs/getting_started/overview