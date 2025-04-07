# 基础信息

|      |      |
|------|------|
| 名称 | CountingInversions |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/divideandconquer/CountingInversions.java |
| 包名 | com.thealgorithms.divideandconquer |
| 依赖项 | [] |
| 概述说明 | 归并排序计算数组逆序对数量。 |

# 说明

该代码实现了一个通过归并排序算法来计算数组中逆序对数量的功能。归并排序在排序过程中能够有效地统计数组中逆序对的数量，逆序对指的是数组中前一个元素大于后一个元素的组合。该算法通过分治策略将数组不断分割，直到最小单位，然后在合并过程中统计逆序对的数量，最终返回数组中所有逆序对的总数。这种方法在时间效率上较为优越，适合处理大规模数据。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| CountingInversions | class | 该代码通过归并排序计算数组中逆序对的数量。 |



## 类 CountingInversions

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | CountingInversions |
| 说明 | 该代码通过归并排序计算数组中逆序对的数量。 |


### UML类图

```mermaid
classDiagram
    class CountingInversions {
        +CountingInversions()
        +int countInversions(int[] arr)
        -int mergeSortAndCount(int[] arr, int left, int right)
        -int mergeAndCount(int[] arr, int left, int mid, int right)
    }
```

这段代码定义了一个名为 `CountingInversions` 的类，用于计算数组中逆序对的数量。该类包含一个私有的构造函数，确保无法实例化该类。主要功能通过 `countInversions` 方法实现，该方法调用 `mergeSortAndCount` 进行递归的归并排序，并在排序过程中计算逆序对的数量。`mergeAndCount` 方法用于合并两个已排序的子数组，并计算它们之间的交叉逆序对。整个流程通过归并排序的方式高效地计算逆序对的数量。


### 内部方法调用关系图

```mermaid
graph TD
    A["类CountingInversions"]
    B["构造方法: CountingInversions()"]
    C["方法: countInversions(int[] arr)"]
    D["方法: mergeSortAndCount(int[] arr, int left, int right)"]
    E["方法: mergeAndCount(int[] arr, int left, int mid, int right)"]
    F["条件: left >= right"]
    G["计算mid: mid = left + (right - left) / 2"]
    H["递归调用: mergeSortAndCount(arr, left, mid)"]
    I["递归调用: mergeSortAndCount(arr, mid + 1, right)"]
    J["调用: mergeAndCount(arr, left, mid, right)"]
    K["返回: inversions"]
    L["创建数组: leftArr = new int[mid - left + 1]"]
    M["创建数组: rightArr = new int[right - mid]"]
    N["复制数组: System.arraycopy(arr, left, leftArr, 0, mid - left + 1)"]
    O["复制数组: System.arraycopy(arr, mid + 1, rightArr, 0, right - mid)"]
    P["初始化: i = 0, j = 0, k = left, inversions = 0"]
    Q["循环: while (i < leftArr.length && j < rightArr.length)"]
    R["条件: leftArr[i] <= rightArr[j]"]
    S["赋值: arr[k++] = leftArr[i++]"]
    T["赋值: arr[k++] = rightArr[j++]"]
    U["增加: inversions += mid + 1 - left - i"]
    V["循环: while (i < leftArr.length)"]
    W["赋值: arr[k++] = leftArr[i++]"]
    X["循环: while (j < rightArr.length)"]
    Y["赋值: arr[k++] = rightArr[j++]"]
    Z["返回: inversions"]

    A --> B
    A --> C
    C --> D
    D --> F
    F -->|true| K
    F -->|false| G
    G --> H
    H --> I
    I --> J
    J --> K
    J --> L
    L --> M
    M --> N
    N --> O
    O --> P
    P --> Q
    Q --> R
    R -->|true| S
    S --> Q
    R -->|false| T
    T --> U
    U --> Q
    Q -->|false| V
    V --> W
    W --> V
    V -->|false| X
    X --> Y
    Y --> X
    X -->|false| Z
```

这段代码实现了一个计算数组中逆序对数量的算法。通过使用修改后的归并排序方法，递归地将数组分成两半，分别排序并计算逆序对，最后合并两个子数组并计算跨子数组的逆序对。流程图展示了类中的方法调用关系以及主要逻辑步骤的执行顺序。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| mergeAndCount | int | 合并数组并计算逆序数。 |
| countInversions | int | 静态方法计算数组逆序数，调用归并排序实现。 |
| mergeSortAndCount | int | 实现归并排序并计算逆序数的递归方法。 |




