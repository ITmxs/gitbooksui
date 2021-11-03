# Windows环境安装Flutter

## Windows 系统要求

要在 Windows 系统上安装和运行 Flutter，您首先需要满足您的开发环境的这些要求。

| **操作系统**     | Windows 7 或更高版本（我是 Windows 10。您也可以使用 Mac 或 Linux 操作系统。）。 |
| ---------------- | ------------------------------------------------------------ |
| **磁盘空间**     | 400 MB（不包括用于 IDE/工具的磁盘空间）。                    |
| **工具**         | 1. Windows PowerShell 2. Git for Windows 2.x（此处，从 Windows 命令提示符选项使用 Git）。 |
| **开发工具包**   | 适用于 Windows 的 Flutter SDK                                |
| **集成开发环境** | Android Studio（官方），Vscode                               |



## 安装 Flutter SDK

**第一步：**下载Flutter Software Development Kit for windows的安装包。要下载 Flutter SDK，请访问其官方[网站](https://flutter.dev/)，单击**Get started**按钮，您将看到以下屏幕。

**第 2 步：**接下来，要下载最新的 Flutter SDK，请单击 Windows**图标**。在这里，您将找到[SDK](https://flutter.dev/docs/get-started/install/windows)的下载链接。

**第 3 步：**下载完成后，解压**zip**文件并将其放置在所需的安装文件夹或位置，例如 D:/Flutter。

#### **注意：** Flutter SDK 不应该放在需要管理员权限的地方。

**第 4 步：**要在常规 Windows 控制台中运行 Flutter 命令，您需要更新系统路径以包含 flutter bin 目录。执行此操作需要执行以下步骤：

**步骤 4.1：**转到 MyComputer 属性 -> 高级选项卡 -> 环境变量。您将看到以下屏幕。

**Step 4.2:** Now, select path -> click on edit. The following screen appears.

**步骤4.3：**在上面的窗口中，点击新建->变量值中Flutter bin文件夹的写入路径->确定->确定->确定。

**第 5 步：**现在，运行 $ **flutter doctor**命令。此命令检查 Flutter 应用程序开发的所有要求，并显示 Flutter 安装状态报告。

**第 6 步：**当您运行上述命令时，它将分析系统并显示其报告，如下图所示。在这里，您将找到运行 Flutter 所需的所有缺失工具的详细信息，以及可用但未与设备连接的开发工具。