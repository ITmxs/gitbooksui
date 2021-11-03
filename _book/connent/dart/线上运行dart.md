## 使用 DartPad 在线运行 Dart 程序

您可以使用 https://dartpad.dartlang.org/ 上提供的在线 Dart 编辑器在线运行您的 Dart 程序。Dart 编辑器执行脚本并显示 HTML 和控制台输出。Dartpad 编辑器还包含一些示例程序以供学习。Dartpad 在线编辑器如下所示 –

![image-20211009093524201](D:\study_manger\flutter\images\image-20211009093524201.png)



在本教程中，您将通过实际示例了解 Dart Hello World 程序及其应用。

## Dart 你好世界

“世界你好！” program 是一个最简单的程序，它会在屏幕上显示一些文本。“世界你好！” program 是一个简单但完整的程序，适合初学者，它说明了任何编程语言的基本语法。“世界你好！” 程序为您提供了一种测试系统和编程环境的方法。本教程将指导您使用 Dart 编程语言编写一个基本的“Hello, World”程序。

## 先决条件

在开始本教程之前，我们假设您已经安装了 Dart SDK（如果您没有安装 Dart SDK，请在开始之前安装它）并且必须在您的计算机上设置本地编程环境。

## 创建 Dart Hello World 程序

**第 1 步：-**使用您选择的文本编辑器程序创建一个名为**“helloworld.dart”**的文件。该**.dart**文件扩展名是用于指定Dart程序文件。

**Step 2:-**打开我们创建的**“helloworld.dart”**文件，将下面这行代码放入并保存。

```dart
// luckly - Hello World!
// 这是我的第一个demo

main(){
 print("luckly - Hello World!");
}
```

让我们了解上述程序的每个部分。

**1. 注释**——这是用于提供有关我们创建的程序的信息的注释语句。

```
// luckly - Hello World!
// 这是我的第一个demo
```

**2. main()** ——它是我们程序执行开始的入口点。它是程序开始执行的特殊、必需的顶级函数。



**3. print()** – print() 函数用于将双引号之间的内容输出/显示到屏幕上。print() 方法类似于 Perl、Java 或任何其他语言。

```
print("luckly - Hello World!");
```



## 运行 Dart 程序

**第 3 步：**现在，编译并运行上面的 Dart 程序

程序执行后会打印

```
luckly - Hello World!
```

