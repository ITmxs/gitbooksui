# Dart – 反转列表



## Dart – 反转列表

您可以通过使用内置函数或使用具有交换机制的循环语句来反转 Dart 中的列表。

反转 List 会使第一个元素放在最后一个位置，第二个元素放在最后一个位置，依此类推。

一种特殊情况是，当您反转按升序排序的数字列表时，生成的反转列表将按降序排列。

在本教程中，我们将介绍一些反转 Dart 列表的方法。

### 使用 List.reversed 反转 Dart 列表

List.reversed 以相反的顺序返回此列表中对象的 Iterable。我们可以使用这个迭代器来初始化一个新的 List。

在下面的 Dart 程序中，我们获取一个列表并使用构造函数初始化一个新列表，并将`new List.from()`可迭代的反向列表作为参数传递给构造函数。

**Dart**

```
void main(){
    //a list
    var myList = [24, 56, 84, 92];
     
    //intialize a new list from iterable to the items of reversed order
    var reversedList = new List.from(myList.reversed);
     
    print(reversedList);
}
```

**输出**

```
D:\Jianguo\workspace\dart_tutorial>dart example.dart``[92, 84, 56, 24]
```

列表的元素被反转。

### 通过在 For 循环中交换就地反转 Dart 列表

我们可以使用 for 循环迭代到列表的中间，并且对于每次迭代，我们将索引处的元素与 处的元素交换`N-1-index`。

当我们在原始列表中执行此操作时，原始列表最终将具有反向列表。因此，这称为就地反转 Dart 列表。

在下面的 Dart 程序中，我们将使用 for 循环和交换就地反转列表。



**Dart**

```
void main(){
    var myList = [24, 56, 84, 92];
     
    for(var i=0;i<myList.length/2;i++){
        var temp = myList[i];
        myList[i] = myList[myList.length-1-i];
        myList[myList.length-1-i] = temp;
    }
     
    print(myList);
}
```

**输出**

```
D:\Jianguo\workspace\dart_tutorial>dart example.dart``[92, 84, 56, 24]
```

执行 for 循环后的原始列表包含反向列表。

### 使用反向列表反转 Dart 列表作为新列表并保存原始列表

此外，我们可以以某种原始方式反转列表。这里我们创建一个大小与原始列表相同的空列表，并将原始列表中的元素从末尾开始一个一个地复制到新列表中。

**Dart**

```
void main(){
    var myList = [24, 56, 84, 92];
     
    var reversedList = new List(myList.length);
     
    for(var i=0;i<myList.length;i++){
        reversedList[i] = myList[myList.length-1-i];
    }
     
    print(reversedList);
}
```

**输出**

```
D:\Jianguo\workspace\dart_tutorial>dart example.dart``[92, 84, 56, 24]
```

### 结论

在这个Dart 教程中，我们学习了如何使用 List.reversed 反转列表、带交换的 for 循环以及将元素从原始元素复制到反转元素的原始方法。