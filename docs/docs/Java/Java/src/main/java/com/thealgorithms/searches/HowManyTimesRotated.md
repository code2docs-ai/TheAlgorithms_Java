# 基础信息

|      |      |
|------|------|
| 名称 | HowManyTimesRotated |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/searches/HowManyTimesRotated.java |
| 包名 | com.thealgorithms.searches |
| 依赖项 | ['java.util.Scanner'] |
| 概述说明 | Java程序通过二分查找确定数组旋转次数。 |

# 说明

该内容描述了一个Java程序，其功能是计算数组的旋转次数。程序通过二分查找算法来确定数组中的旋转点，从而计算出旋转的次数。二分查找是一种高效的搜索方法，能够在有序或部分有序的数组中快速定位目标元素或特定位置。在此场景中，旋转点是指数组从有序状态被旋转后的分界点，通过找到这个点，程序可以准确地计算出数组被旋转的次数。这一过程充分利用了二分查找的优势，提高了计算效率。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| HowManyTimesRotated | class | Java程序计算数组旋转次数，使用二分查找确定旋转点。 |



## 类 HowManyTimesRotated

|      |      |
|------|------|
| 访问范围 | final |
| 类型 | class |
| 名称 | HowManyTimesRotated |
| 说明 | Java程序计算数组旋转次数，使用二分查找确定旋转点。 |


### UML类图

```mermaid
classDiagram
    class HowManyTimesRotated {
        -HowManyTimesRotated()
        +main(String[] args)
        +rotated(int[] a) int
    }
```

**描述：**  
`HowManyTimesRotated` 类是一个工具类，用于计算一个已排序数组被旋转的次数。该类包含一个私有的构造函数，防止实例化。`main` 方法从标准输入读取数组并调用 `rotated` 方法计算旋转次数，然后输出结果。`rotated` 方法使用二分查找算法来确定数组的旋转点，并返回旋转次数。该类没有依赖其他类，功能独立且简洁。


### 内部方法调用关系图

```mermaid
graph TD
    A["类HowManyTimesRotated"]
    B["私有构造方法: HowManyTimesRotated()"]
    C["main方法: main(String[] args)"]
    D["创建Scanner对象: Scanner sc = new Scanner(System.in)"]
    E["读取整数n: int n = sc.nextInt()"]
    F["创建数组a: int[] a = new int[n]"]
    G["循环读取数组元素: for (int i = 0; i < n; i++)"]
    H["读取数组元素: a[i] = sc.nextInt()"]
    I["调用rotated方法: rotated(a)"]
    J["输出结果: System.out.println('The array has been rotated ' + rotated(a) + ' times')"]
    K["关闭Scanner: sc.close()"]
    L["方法rotated: rotated(int[] a)"]
    M["初始化变量: int low = 0, int high = a.length - 1, int mid = 0"]
    N["循环查找旋转点: while (low <= high)"]
    O["计算mid: mid = low + (high - low) / 2"]
    P["判断旋转点: if (a[mid] < a[mid - 1] && a[mid] < a[mid + 1])"]
    Q["找到旋转点: break"]
    R["调整high: high = mid + 1"]
    S["调整low: low = mid - 1"]
    T["返回旋转点: return mid"]

    A --> B
    A -.-> C
    C --> D
    C --> E
    C --> F
    C --> G
    G --> H
    C --> I
    C --> J
    C --> K
    A --> L
    L --> M
    L --> N
    N --> O
    N --> P
    P --> Q
    P --> R
    P --> S
    L --> T
```

这段代码定义了一个名为`HowManyTimesRotated`的类，用于计算一个已排序数组被旋转的次数。代码通过二分查找算法在数组中寻找旋转点，并返回该点的索引。`main`方法负责读取用户输入的数组并调用`rotated`方法进行计算，最后输出旋转次数。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| main | void | Java程序读取数组并输出旋转次数。 |
| rotated | int | 使用二分查找法在旋转数组中查找最小值的索引。 |




