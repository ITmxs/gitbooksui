# Dart – 加入两个列表

## Dart – 加入两个列表

您可以通过多种方式在 Dart 中连接两个列表。在本教程中，我们将通过两种方法来连接列表。

第一个是使用 List.addAll()。将列表作为参数传递给 addAll() 方法，您希望将其附加到此列表中。

第二种方式是遍历第二个列表并在迭代过程中将元素添加到第一个列表中。

### 使用 List.addAll() 在 Dart 中加入列表

在此示例中，我们采用两个列表`list1`和`list2`。然后使用 addAll() 附加`list2`到`list1`.

List.addAll() 修改此列表。所以list1 被修改，即list2 的元素被附加到list1。

**Dart**

```
void main(){
    List list1 = [24, 'Hello', 84];
    List list2 = [41, 65];
     
    //join list2 to list1
    list1.addAll(list2);
     
    print(list1);
}
```

**输出**

```
[24, Hello, 84, 41, 65]
```

### 将其他列表的元素一一添加到第一个列表

这是连接两个列表的原始方式。在这里，我们遍历`list2`使用 forEach 的每个元素并将这些元素添加到`list1`.

**Dart**

```
void main(){
    List list1 = [24, 'Hello', 84];
    List list2 = [41, 65];
     
    //join list2 to list1
    list2.forEach((element) => list1.add(element));
     
    print(list1);
}
```

**输出**

```
[24, Hello, 84, 41, 65]
```

### 结论

在本Dart 教程中]，我们学习了如何使用 List.addAll() 和 List.add() 方法将一个列表附加或连接到另一个列表。