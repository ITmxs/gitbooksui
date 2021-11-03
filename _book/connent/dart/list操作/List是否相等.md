# Dart - 检查两个列表的相等性

<iframe frameborder="0" src="https://463eb74d39ca1706d3ed6433ca2b4a70.safeframe.googlesyndication.com/safeframe/1-0-38/html/container.html" id="google_ads_iframe_/8691100/Jianguo_S2S_Rectangle_Tutorial_Mid_0" title="第三方广告内容" name="" scrolling="no" marginwidth="0" marginheight="0" width="300" height="250" data-is-safeframe="true" sandbox="allow-forms allow-popups allow-popups-to-escape-sandbox allow-same-origin allow-scripts allow-top-navigation-by-user-activation" data-google-container-id="1" data-load-complete="true" style="max-width: 100%; border: 0px; vertical-align: bottom;"></iframe>

## Dart – 检查列表是否相等

您可以检查两个列表的元素是否相等。

让我们考虑如果两个列表在整个长度上具有相同的元素，则它们是相等的。

### 检查两个列表是否相等元素

在这个例子中，我们取了三个列表，其中两个列表的内容相等，第三个列表与前两个不同。

我们将编写一个函数 areListsEqual() 来检查给定的两个列表是否逐个元素相等。作为先决条件，我们检查给定的变量是否都是列表，然后比较它们的长度。

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
list1 and list2 are equal.``list1 and list3 are not equal.
```

### 结论

在本Dart 教程中，我们学习了如何检查两个 List 的值是否相等。