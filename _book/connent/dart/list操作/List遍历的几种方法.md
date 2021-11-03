## Dart List – 迭代元素

在处理列表时，大多数时候我们可能需要遍历或迭代列表的元素。

在本教程中，我们将学习一些迭代 Dart 列表元素的方法。



使用 for 循环和索引，您可以从第一个元素开始到最后一个元素结束，将索引从 0 递增到列表的长度。

使用 List.forEach，您可以为列表的每个元素应用一个函数。

您可以获得列表元素的可迭代对象，并使用带有可迭代对象的 while 循环来迭代元素。

### 方式一使用 For 循环遍历 Dart 列表

在下面的 Dart 程序中，我们使用一个包含一些元素的列表。然后我们使用带有索引的 Dart For 循环遍历列表的所有元素。在每次迭代期间，我们只打印元素，证明我们可以访问该元素。

```
void main(){
    //list
    var myList = [25, 63, 84];
     
    //traverse through each element of list
    for(var i=0;i<myList.length;i++){
        print(myList[i]);
    }
}
```

**输出**

```

25
63
84
```

因此，我们可以使用 for 循环遍历列表项。

### 方式二使用 forEach 迭代 Dart 列表

在下面的 Dart 程序中，我们为列表的每个元素应用打印函数。

```
void main(){
    var myList = [24, 63, 84];
     
    myList.forEach((element) => 
        print(element)
    );
}
```



**输出**

```

25
63
84
```



### 方式三使用 Iterator 和 While 循环遍历 Dart 列表

类似Java中的iteator    

在下面的 Dart 程序中，我们获取列表的迭代器并将其存储在一个变量中。然后在while循环中使用这个变量在每次迭代期间移动到下一个元素并访问该元素。在这个例子中，我们只是打印出元素。

```
void main(){
    //list
    var myList = [25, 63, 84];
     
    //get iterator to the list
    var myListIter = myList.iterator;
     
    //iterate over the list
    while(myListIter.moveNext()){
        print(myListIter.current);
    }
}
```

**输出**

```

25
63
84
```

### 方式四 增强for循环

循环遍历 List 中的数据

```
void main(){
    //list
    var myList = [25, 63, 84];
     
   for (var value in myList) {
  //value 就是List中对应的值
        print(value);
}

}
```

您还可以为每个元素应用用户定义的函数，而不是我们在上述程序中使用的打印函数。

```
void processingFunc(var element){
    //processing or transformation on the element
    var x=element%2;
    print(x);
}
 
void main(){
    var myList = [24, 63, 84];
     
    myList.forEach((element) => 
        processingFunc(element)
    );
}
```

**输出**

```
0
1
0
```

我们只是为列表中的每个元素计算了除以 2 时的提醒。



### 结论

在本节中，我们学习了四种如何迭代 Dart 列表的方法。