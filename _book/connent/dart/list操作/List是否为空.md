## Dart - 检查列表是否为空

空列表意味着列表中没有元素。

有很多方法可以检查这一点。

空列表的长度属性返回零。

或者您可以使用内置属性`List.isEmpty`。`List.isEmpty`如果列表为空，则返回 true，否则返回 false。

我们还有一个内置属性来检查列表是否为空。但是这个检查列表是否不是空的。该物业是 `List.isNotEmpty`。

在本教程中，我们将通过这三种方法来查找列表是否为空。

### 使用 Length 属性检查 Dart 列表是否为空

在下面的 dart 程序中，我们编写了一个函数`checkList()`，它接收列表作为参数。它检查长度并根据返回值决定列表是否为空。

在主函数中，我们`checkList()`将为空列表和非空列表调用函数。

**Dart**

```
void checkList(var myList){
    //length of empty list is zero
    if(myList.length == 0){
        print("List "+myList.toString()+" is empty");
    } else{
        print("List "+myList.toString()+" is not empty");
    }
}
 
void main(){
    var list1 = [];
    checkList(list1);
     
    var list2 = [24, 56, 84];
    checkList(list2);
}
```

**输出**

```
D:\Jianguo\workspace\dart_tutorial>dart example.dart``List [] is empty``List [24, 56, 84] is not empty
```

结果是显而易见的。列表 [] 为空，列表 [24, 56, 84] 不为空。

### 使用 isEmpty 属性检查 Dart 列表是否为空

在下面的 Dart 程序中，我们将使用`isEmpty`List 类的属性来判断列表是否为空。

**Dart**



```
void checkList(var myList){
    //isEmpty returns true if list is emtpy
    if(myList.isEmpty){
        print("List "+myList.toString()+" is empty");
    } else{
        print("List "+myList.toString()+" is not empty");
    }
}
 
void main(){
    var list1 = [];
    checkList(list1);
     
    var list2 = [24, 56, 84];
    checkList(list2);
}
```

**输出**

```
D:\Jianguo\workspace\dart_tutorial>dart example.dart``List [] is empty``List [24, 56, 84] is not empty
```

### 使用 isNotEmpty 属性检查 Dart 列表是否为空

这与前面的示例相同，但我们使用的`isNotEmpty`是 List 类的属性。

**Dart**

```
void checkList(var myList){
    //isEmpty returns true if list is emtpy
    if(myList.isNotEmpty){
        print("List "+myList.toString()+" is not empty");
    } else{
        print("List "+myList.toString()+" is empty");
    }
}
 
void main(){
    var list1 = [];
    checkList(list1);
     
    var list2 = [24, 56, 84];
    checkList(list2);
}
```

**输出**

```
D:\Jianguo\workspace\dart_tutorial>dart example.dart``List [] is empty``List [24, 56, 84] is not empty
```

### 结论

在这个[Dart 教程中](https://www.Jianguo.com/dart/)，我们学习了一些使用一些内置函数检查列表是否为空或不在 Dart 中的方法。