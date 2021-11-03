在本教程中，您将通过实际示例了解 Dart Sets 及其应用。

## Dart 套装

在 Dart 中，Set 是相同类型的不同值的无序列表。集合与数组非常相似，但它是无序的，不允许重复元素，集合中包含的每个值都是唯一的。Dart 集合是类型化的，因此一旦您声明了集合的类型或 Dart 推断出它，那么您将只有相同类型的元素。当我们想在单个变量中保存单一数据类型的不同值并且项目的顺序并不重要时，集合很有用。







## Dart 声明/初始化集

有两种方法可以声明/初始化一个空集，`{}`在类型参数前面使用，或分配`{}`给类型变量`Set.`

```
var setName = &lt;type&gt;{};
```



或者

```
Set&lt;type&gt; setName = {};
```



这里，**SetName**替换为 set 变量的名称，**type**替换为 set 的数据类型。

**注意：- 映射文字的语法类似于集合文字的语法。如果您忘记了使用 {} 或分配给它的变量的类型注释，那么 Dart 将创建一个 Map 对象而不是 Set。**



```
// var names = {}; // Creates a map, not a set.
```



**例子：-**



```
void main() { 
  var persons = &lt;String&gt;{"John", "Doe", "Smith", "Alex"};
  print("W3Adda - Dart Declare/Initialize Set.");
  print(persons);
}
```



**输出：-**



![dart_declaring_set](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_declaring_set.jpg)

## 将元素添加到集合中

在 Dart 中，**add()**或**addAll()**函数用于在给定的集合中添加或插入项目。add() 方法用于将单个项目插入到现有集合中，而 addAll() 方法用于将多个项目添加到给定集合中。集合中的重复值将被忽略。

**句法：-**



```
set_name.add(&lt;value&gt;);
```



**例子：-**



```
void main() { 
  var names = {"John", "Doe", "Smith", "Alex"};
  var persons = &lt;String&gt;{};
  print("W3Adda - Dart insert Item(s) into Set.");
  persons.add("Murphy");
  print(persons);
  persons.addAll(names);
  print(persons);
}
```



**输出：-**



![dart_add_item_in_set_add_method_new](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_add_item_in_set_add_method_new.jpg)

## Dart 在索引处获取集合元素

所述**的ElementAt（）**方法用于在指定的索引的位置来得到产品。Set 的索引从零 (0) 开始到 Set 的最后一个元素，即**size – 1**，其中**size**是一个集合中的元素数。如果您输入的数字大于最大索引，则会引发错误。

**句法：-**



```
set_name.elementAt(&lt;index&gt;);
```





**例子：-**



```
void main() { 
  var persons = &lt;String&gt;{"John", "Doe", "Smith", "Alex"};
  var p = persons.elementAt(2);
  print("W3Adda - Dart Get Item at Index.");
  print(p);
}
```



**输出：-**



![dart_get_item_at_index](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_get_item_at_index.jpg)

## Dart 获取集合元素计数

在 Dart 中，**lenth**属性可用于查找集合中元素的数量。

**句法：-**



```
set_name.length;
```



**例子：-**



```
void main() { 
  var persons = &lt;String&gt;{"John", "Doe", "Smith", "Alex"};
  var l = persons.length;
  print("W3Adda - Dart Get Set Length.");
  print(l);
}
```



**输出：-**





![dart_get_set_length](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_get_set_length.jpg)

## Dart 在集合中查找元素

Dart **contains()**方法可用于在集合中查找元素，它需要在集合中查找相同类型的单个元素，并返回一个布尔值来指示给定元素是否存在。

**句法：-**



```
set_name.contains(&lt;value&gt;)
```



**例子：-**



```
void main() { 
  var persons = &lt;String&gt;{"John", "Doe", "Smith", "Alex"};
  print("W3Adda - Dart find an Item in set.");
  if(persons.contains("Doe")){
    print("Given element found.");
  }
  else{
    print("Given element not found.");
  }
}
```



**输出：-**

![dart_set_find_using_contains](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_set_find_using_contains.jpg)

## Dart 移除集合元素

在 Dart 中，**remove()**方法用于从给定集合中移除或删除元素。



```
set_name.contains(&lt;value&gt;)
```



**句法：-**

**例子：-**



```
void main() { 
  var persons = &lt;String&gt;{"John", "Doe", "Smith", "Alex"};
  print("W3Adda - Dart remove an element from set.");
  print("Before Delete");
  print(persons);
  print("After Delete");
  persons.remove("Doe");
  print(persons);
}
```



**输出：-**

![dart_remove_set_element](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_remove_set_element.jpg)

## Dart 迭代集合元素

在 Dart 中，我们可以使用**forEach**方法循环遍历集合元素，如下所示：

**例子：-**



```
void main() { 
  var persons = &lt;String&gt;{"John", "Doe", "Smith", "Alex"};
  print("W3Adda - Dart Iterating Set Elements.");
  persons.forEach((value) {
    print('Value: $value');
  });
}
```



**输出：-**

![dart_iterating_set_elements](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_iterating_set_elements.jpg)

## Dart 删除所有集合元素

的**明确（）**方法被用来去除或从给定组全部删除。

**句法：-**



```
set_name.clear();
```



**例子：-**



```
void main() { 
  var persons = &lt;String&gt;{"John", "Doe", "Smith", "Alex"};
  print("W3Adda - Dart remove all elements from set.");
  print("Before Clear");
  print(persons);
  print("After Clear");
  persons.clear();
  print(persons);
}
```



**输出：-**

![dart_clear_remove_all_set_elements](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_clear_remove_all_set_elements.jpg)

## Dart 转换集到列表

Dart`toList()`方法用于将 Set 对象转换为 List 对象。的类型`List`必须与`Set`元素的类型相同。

**句法：-**



```
List&lt;type&gt; &lt;list_name&gt;= &lt;set_name&gt;.toList();
```





## Dart 操作

在 Dart 中，我们可以对任何**Set**执行以下一些基本的 set 操作**——
**

**Union :-**两个集合 a 和 b 的并集是集合 a 和 b 的组合值。

**交集：-**两个集合 a 和 b 的交集是一个包含两个集合中所有公共元素的集合。

**减法：-**两个集合 a 和 b 的减法集合包含集合 a 的所有元素并删除属于集合 b 的元素。

**例子：-**



```
void main() { 
var a = &lt;int&gt;{10,12,14,16,18};
var b = &lt;int&gt;{5,7,9,11,13};
var c = &lt;int&gt;{2,3,5,7};
print("W3Adda - Dart Set Operations");
print("b union a is");
print(b.union(a));
print("b intersection a is");
print(b.intersection(a));
print("b difference c is");
print(b.difference(c));
}
```



**输出：-**

![dart_set_operations](https://luckly007.oss-cn-beijing.aliyuncs.com/image/dart_set_operations.jpg)

## Dart Sets属性

下面是 Dart Sets 支持的属性列表。

| **PROPERTY** | 描述                                                      |
| :----------- | :-------------------------------------------------------- |
| `first`      | 它返回集合中的第一个元素。                                |
| `isEmpty`    | 如果集合没有元素，则返回 true。                           |
| `isNotEmpty` | 如果集合至少有一个元素，则返回 true。                     |
| `length`     | 它返回集合的长度/大小，也可以看作是给定集合中元素的数量。 |
| `last`       | 它返回集合中的最后一个元素。                              |
| `hashCode`   | 它返回相应对象的哈希码。                                  |
| `Single`     | 它用于检查集合是否只有一个元素并返回它。                  |

 在本教程中，我们通过实际示例了解了 Dart Sets 及其应用。我希望你会喜欢这个教程。

































