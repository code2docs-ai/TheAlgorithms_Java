# 基础信息

|      |      |
|------|------|
| 名称 | FibonacciSearch |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/searches/FibonacciSearch.java |
| 包名 | com.thealgorithms.searches |
| 依赖项 | ['com.thealgorithms.devutils.searches.SearchAlgorithm'] |
| 概述说明 | FibonacciSearch类用斐波那契数列在有序数组中查找元素，返回索引或-1。 |

# 说明

FibonacciSearch类实现了一种基于斐波那契数列的搜索算法，用于在有序数组中查找指定元素。该算法通过利用斐波那契数列的特性，逐步缩小搜索范围，最终确定目标元素的位置。如果找到目标元素，则返回其索引；若未找到，则返回-1。这种方法在特定情况下比二分查找更高效，尤其适用于大规模数据集。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| FibonacciSearch | class | FibonacciSearch类实现搜索算法，通过斐波那契数列在有序数组中查找指定元素，返回索引或-1。 |



## 类 FibonacciSearch

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | FibonacciSearch |
| 说明 | FibonacciSearch类实现搜索算法，通过斐波那契数列在有序数组中查找指定元素，返回索引或-1。 |


### UML类图

```mermaid
classDiagram
    class FibonacciSearch {
        +int find(T~Comparable~[] array, T~Comparable~ key)
        -boolean isSorted(Comparable[] array)
    }

    class SearchAlgorithm {
        <<Interface>>
        +int find(T~Comparable~[] array, T~Comparable~ key)
    }

    FibonacciSearch --> SearchAlgorithm : 实现
```

**描述：**  
`FibonacciSearch` 类实现了 `SearchAlgorithm` 接口，提供了斐波那契搜索算法的实现。该算法用于在已排序的数组中查找指定元素的索引。`find` 方法接收一个泛型数组和键值，返回键值在数组中的索引，若未找到则返回 -1。`isSorted` 方法用于检查数组是否已排序。代码中包含了输入验证，确保数组不为空、已排序且键值不为空。


### 内部方法调用关系图

```mermaid
graph TD
    A["类FibonacciSearch"]
    B["方法: int find(T[] array, T key)"]
    C["方法: boolean isSorted(Comparable[] array)"]
    D["检查: array.length == 0"]
    E["抛出异常: IllegalArgumentException('Input array must not be empty.')"]
    F["检查: !isSorted(array)"]
    G["抛出异常: IllegalArgumentException('Input array must be sorted.')"]
    H["检查: key == null"]
    I["抛出异常: IllegalArgumentException('Key must not be null.')"]
    J["初始化: fibMinus1 = 1, fibMinus2 = 0, fibNumber = fibMinus1 + fibMinus2, n = array.length"]
    K["循环: fibNumber < n"]
    L["更新: fibMinus2 = fibMinus1, fibMinus1 = fibNumber, fibNumber = fibMinus2 + fibMinus1"]
    M["初始化: offset = -1"]
    N["循环: fibNumber > 1"]
    O["计算: i = Math.min(offset + fibMinus2, n - 1)"]
    P["比较: array[i].compareTo(key) < 0"]
    Q["更新: fibNumber = fibMinus1, fibMinus1 = fibMinus2, fibMinus2 = fibNumber - fibMinus1, offset = i"]
    R["比较: array[i].compareTo(key) > 0"]
    S["更新: fibNumber = fibMinus2, fibMinus1 = fibMinus1 - fibMinus2, fibMinus2 = fibNumber - fibMinus1"]
    T["返回: i"]
    U["检查: fibMinus1 == 1 && array[offset + 1] == key"]
    V["返回: offset + 1"]
    W["返回: -1"]
    X["循环: i = 1 to array.length"]
    Y["比较: array[i - 1].compareTo(array[i]) > 0"]
    Z["返回: false"]
    AA["返回: true"]

    A --> B
    A --> C
    B --> D
    D -->|是| E
    D -->|否| F
    F -->|是| G
    F -->|否| H
    H -->|是| I
    H -->|否| J
    J --> K
    K -->|是| L
    K -->|否| M
    M --> N
    N -->|是| O
    O --> P
    P -->|是| Q
    P -->|否| R
    R -->|是| S
    R -->|否| T
    N -->|否| U
    U -->|是| V
    U -->|否| W
    C --> X
    X --> Y
    Y -->|是| Z
    Y -->|否| AA
```

这段代码实现了斐波那契搜索算法，用于在有序数组中查找指定元素的索引。首先，代码检查输入数组是否为空、是否有序以及搜索键是否为空，若不符合条件则抛出异常。接着，代码通过斐波那契数列来确定搜索范围，并在循环中不断缩小搜索范围，直到找到目标元素或确定其不存在。最后，代码返回目标元素的索引或-1表示未找到。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| isSorted | boolean | 检查数组是否已按升序排列。 |
| find | int | 实现斐波那契搜索，要求数组非空、有序且键值非空。 |




