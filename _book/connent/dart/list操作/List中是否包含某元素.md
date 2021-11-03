# Dart - 检查列表是否包含元素

## 检查 Dart 列表是否包含元素

您可以检查 Dart 列表中是否存在元素。有很多方法可以检查列表中元素的存在。

**解决方案 1：** List.contains() 是一种方法，它接受一个元素并检查该元素是否存在于该列表中。

**解决方案 2：**迭代列表的元素并检查是否相等。当元素找到匹配项时，您可以打破循环并声明该元素出现在给定列表中。

在本教程中，我们将使用 Dart 程序完成上述解决方案。

### 使用 List.contains() 检查 Dart 列表是否包含元素

如果元素存在于此列表中，则 List.contains(element) 返回 true。否则，它返回false。

在这个 Dart 程序中，我们将获取一个数字列表并检查`84` 此列表中是否存在。我们也将检查号码`77`。

**Dart**

```
bool areListsEqual(var list1, var list2) {
    // check if both are lists
    if(!(list1 is List && list2 is List)
        // check if both have same length
        || list1.length!=list2.length) {
        return false;
    }
     
    // check if elements are equal
    for(int i=0;i<list1.length;i++) {
        if(list1[i]!=list2[i]) {
            return false;
        }
    }
     
    return true;
}
 
void main(){
    List list1 = [24, 'Hello', 84];
    List list2 = [24, 'Hello', 84];
    List list3 = [11, 'Hi', 41];
     
    if(areListsEqual(list1, list2)) {
        print('list1 and list2 are equal in value.');
    } else {
        print('list1 and list2 are not equal in value.');
    }
     
    if(areListsEqual(list1, list3)) {
        print('list1 and list3 are equal in value.');
    } else {
        print('list1 and list3 are not equal in value.');
    }
}
```

**输出**

```
84 is present in the list [24, 56, 84, 92]``77 is not present in the list [24, 56, 84, 92]
```

如`84`列表中所示，`myList.contains(84)`返回 true。

由于`77`列表中不存在，`myList.contains(77)`返回 true。

### 使用 For 循环和相同（）方法检查 Dart 列表是否包含元素

这是检查元素是否存在于列表中的一种非常原始的方法。

**Dart**



```
void main(){
    var myList = [24, 56, "hello", "dart"];
     
    var element = "hello";
     
    var present = false;
    for(var i=0;i<myList.length;i++) {
        // you may have to check the equality operator
        if(element == myList[i]) {
            present=true;
            break;
        }
    }
     
    if(present){
        print('$element is present in the list $myList');
    } else {
        print('$element is not present in the list $myList');
    }
}
```

**输出**

```
hello is present in the list [24, 56, hello, dart]
```

解决方案 1 优于解决方案 2。解决方案 2 只是为了理解还有另一种方法来检查元素是否存在于列表中。

### 结论

在本Dart 教程中，我们学习了如何使用 List.contains() 或 for 循环检查 Dart 列表中是否存在元素。