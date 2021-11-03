1. 为您的开发机器的操作系统下载安装包，以获得 Flutter SDK 的最新稳定版本。
2. 在所需位置提取安装包。
3. 将该`flutter`工具添加到您的路径中。
4. 运行该`flutter doctor`命令，它会提醒您有关 Flutter 安装的任何问题。
5. 安装缺少的依赖项。
6. 使用 Flutter 插件/扩展设置您的 IDE。
7. 试驾一个应用程序。

Flutter 网站上提供的说明做得非常好，让您可以轻松地在您选择的平台上设置开发环境。本教程的其余部分假设您已经为 Flutter 开发设置了 VS Code，并且您已经解决了`flutter doctor`发现的所有问题。您还可以使用 Android Studio 进行操作。

要将您的项目作为移动应用程序运行，您需要使用以下选项之一：

- 运行 iOS 模拟器或 Android 模拟器。
- 为开发设置 iOS 或 Android 设备。
- 将您的代码[作为 Web 应用程序运行](https://flutter.dev/docs/get-started/web)。
- 最后，您可以将代码[作为桌面应用程序运行](https://flutter.dev/desktop)。

即使您的最终目标是移动设备，在开发过程中使用 Web 或桌面应用程序也可以为您提供调整应用程序大小并观察其在各种屏幕尺寸下的外观的优势。



# Flutter安装

在本节中，我们将学习如何为 Flutter 应用程序的成功开发设置环境。





## 安装 Git

**第 1 步：**要下载 Git，[请单击此处](https://git-scm.com/download/win)。

**步骤 2：**运行**.exe**文件以完成安装。在安装过程中，请确保您选择了推荐的选项。



![安装](https://luckly007.oss-cn-beijing.aliyuncs.com/image/flutter-installation.png)

要阅读有关安装 Git 的更多信息，[请单击此处](https://www.javatpoint.com/how-to-install-git-on-windows)。



**第 7 步：**安装 Android SDK。如果 flutter doctor 命令在你的系统中没有找到 Android SDK 工具，那么你需要先安装 Android Studio IDE。要安装 Android Studio IDE，请执行以下步骤。

**步骤 7.1：**从[官方网站](https://developer.android.com/studio/#downloads)下载最新的 Android Studio 可执行文件或 zip 文件。

**步骤 7.2：**下载完成后，打开**.exe**文件并运行它。您将获得以下对话框。

**步骤 7.3：**按照安装向导的步骤进行操作。安装向导完成后，您将看到以下屏幕。

**步骤 7.4：**在上面的屏幕中，单击 Next->Finish。单击“完成”按钮后，您需要选择“不导入设置选项”并单击“确定”。它将启动 Android Studio。

**第 8 步：**接下来，您需要设置一个 Android 模拟器。它负责运行和测试 Flutter 应用程序。

**步骤 8.1：**要设置 Android 模拟器，请转到 Android Studio > 工具 > Android > AVD 管理器，然后选择创建虚拟设备。或者，在搜索框中转到“帮助”->“查找操作”->“键入模拟器”。您将看到以下屏幕。


![颤振安装](https://luckly007.oss-cn-beijing.aliyuncs.com/image/flutter-installation9.png)

**步骤 8.2：**选择您的设备定义并单击下一步。

**步骤 8.3：**选择最新 Android 版本的系统映像，然后单击下一步。

**步骤 8.4：**现在，验证所有 AVD 配置。如果正确，请单击“完成”。出现以下屏幕。

![颤振安装](https://luckly007.oss-cn-beijing.aliyuncs.com/image/flutter-installation10.png)

**步骤 8.5：**最后，单击指向红色矩形的图标。Android 模拟器显示如下屏幕。

![颤振安装](https://luckly007.oss-cn-beijing.aliyuncs.com/image/flutter-installation11.png)

**第 9 步：**现在，安装 Flutter 和 Dart 插件以在 Android Studio 中构建 Flutter 应用程序。这些插件提供了创建 Flutter 应用程序的模板，提供了在 Android Studio 本身中运行和调试 Flutter 应用程序的选项。执行以下步骤来安装这些插件。

**步骤 9.1：**打开 Android Studio，然后转到 File->Settings->Plugins。

**步骤 9.2：**现在，搜索 Flutter 插件。如果找到，请选择 Flutter 插件并单击安装。当您点击安装时，它会要求您安装 Dart 插件，如下图所示。单击是继续。

![颤振安装](https://luckly007.oss-cn-beijing.aliyuncs.com/image/flutter-installation12.png)

**步骤 9.3：**重启 Android Studio。



