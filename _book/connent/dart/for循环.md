## Dart For 循环

欢迎来到 Dart For 循环教程。

在本教程中，我们将学习如何编写 for 循环和一些 Dart 示例程序，以了解 Dart For 循环的用法。

### Dart For 循环的语法

以下是 Dart 编程语言中 For 循环的语法。

```
for (initialization; boolean_expression; update) {
     //statement(s)
 
 }
```

`initialization` 部分可以包含一个或多个正在初始化的变量。

根据`boolean_expression`每次迭代期间的输出，决定是否执行for循环中的语句。如果 `boolean_expression` 计算结果为`true`，则执行 for 循环内的语句。如果 `boolean_expression` 计算结果为`false`，则不执行 for 循环内的语句。

`update` 部分可以包含对变量的更新，例如增量、减量或它们值的任何类型的更改。

### For循环的工作

1. 当程序控制遇到 for 循环语句时，它执行初始化块。

2. 然后评估

   ```
   boolean_expression
   ```

   .

   1. 如果 

      ```
      boolean_expression
      ```

       评估为

      ```
      true
      ```

      ，

      1. 然后执行for循环内的语句。
      2. 然后执行更新部分。
      3. 现在转到**第 2 步**。

   2. 如果 `boolean_expression` 评估为`false`，

   3. 跳出圈套。

### Dart For 循环计算一个数字的阶乘

在下面的示例中，我们将使用 Dart For Loop 来计算给定数字的阶乘。

**Dart示例**

```
void main(){
    var n = 6;
    var factorial = 1;
     
    //for loop to calculate factorial
    for(var i=2; i<=n; i++) {
        factorial = factorial*i;
    }
     
    print('Factorial of ${n} is ${factorial}');
}
```

**输出**

```
Factorial of 6 is 720
```

## Dart 嵌套 For 循环

你可以在 Dart 的另一个 For 循环中编写一个 For 循环。这个过程称为嵌套。因此嵌套 For 循环。

### Dart For 循环打印 * 三角形

在下面的示例中，我们将使用 Dart For Loop 将 *s 转换为直角三角形。

**Dart示例**

```
import 'dart:io';
 
void main(){
    var n = 6;
     
    print('');
     
    for(var i=1; i<=n; i++) {
        for(var j=0; j<i; j++) {
            stdout.write(' *');
        }
        print('');
    }
}
```

**输出**

**注意**：这里我们使用 stdout.write() 写入控制台，末尾没有换行符，这与 print() 不同。

### 结论

在这个[Dart 教程中](https://www.Jianguo.com/dart/)，我们在示例程序的帮助下学习了语法和如何使用 for 循环。