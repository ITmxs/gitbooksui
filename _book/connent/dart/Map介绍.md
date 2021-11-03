# Dart Map

在本教程中，您将通过实际示例了解 Dart Map 及其应用。

## Dart Map

Map 是一个对象，用于将一组值表示为键值对。在Map中，keys和values都可以是任何类型的对象，keys和values都可以是同一种类型的对象没有必要。。在Map中，每个key只能出现一次，但是同一个value可以多次使用. 在 Map 中，每个值都与一个唯一的键相关联，这个键用于访问对应的 Map 值。可以使用大括号 ({ }) 定义 Map，并且可以使用方括号 ([]) 分配和访问值。



```

var weekDays = {'Day1': 'Mon', 'Day2': 'Tue', 'Day3': 'Wed', 'Day4': 'Thu'};
```







## 在 Dart 中声明 Map

在 Dart 中，可以通过以下两种方式声明 Map：

- 使用 Map文字
- 使用 Map 构造函数

## 使用 Map Literals 声明 Map

在 Dart 中，我们可以声明一个带有 Map文字的 Map，如下所示：

**句法：-**

```
	
var <map_name> = {key1:value1, key2:value2,..., key_n:value_n}
```



在这里，映射文字是一个键值对列表，用逗号分隔，用一对花括号**({ })**包围。键值对是由冒号**(:)**分隔的键和值的组合。

**例子：-**

```
var weekDays = {'mon': 'Monday', 'tue': 'Tuesday', 'wed': 'Wednesday', 'thu': 'Thursday', 'fri': 'Friday', 'sat': 'Saturday', 'sun': 'Sunday'};

```





## 使用 Map Constructor 声明/初始化 Map

在 Dart 中，我们可以使用映射构造函数声明/初始化映射，如下所示：

**句法 ：-**

声明一个空映射如下 -

```
var &amp;lt;map_name&amp;gt; = new Map();
```



现在，让我们按如下方式初始化 Map -

```
map_name[key] = value;
```



**例子：-**

```
void main() { 
  var weekDays = new Map();
  weekDays['mon']  = "Monday";
  weekDays['tue']  = "Tuesday";
  weekDays['wed']  = "Wednesday";
  weekDays['thu']  = "Thursday";
  weekDays['fri']  = "Friday";
  weekDays['sat']  = "Saturday";
  weekDays['sun']  = "Sunday";
  print(weekDays);
}
```



**输出：-**

```
{mon: Monday, tue: Tuesday, wed: Wednesday, thu: Thursday, fri: Friday, sat: Saturday, sun: Sunday}
```







##  Map属性

下面是 Dart Map 支持的属性列表。

| **PROPERTY** | 描述                                           |
| :----------- | :--------------------------------------------- |
| `Keys`       | 返回一个可迭代对象，表示相应 Map对象中的所有键 |
| `Values`     | 返回一个可迭代对象，表示相应 Map对象中的所有值 |
| `Length`     | 返回 Map的大小                                 |
| `isEmpty`    | 如果 Map 是空 Map，则返回 true                 |
| `isNotEmpty` | 如果 Map 至少有一项，则返回 true。             |

##  Map方法

下面是 Dart Map 支持的常用方法列表。



| **PROPERTY** | 描述                                     |
| :----------- | :--------------------------------------- |
| `addAll()`   | 将所有键值对添加到此映射中。             |
| `clear()`    | 从 Map中删除所有键值对。                 |
| `remove()`   | 从 Map中删除键及其关联的值（如果存在）。 |
| `forEach()`  | 迭代并将函数应用于映射的每个键值对。     |

 在本教程中，我们通过实际示例了解了 Dart Map 及其应用。我希望你会喜欢这个教程。