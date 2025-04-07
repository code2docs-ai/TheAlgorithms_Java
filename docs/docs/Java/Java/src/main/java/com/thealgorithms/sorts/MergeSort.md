# 基础信息

|      |      |
|------|------|
| 名称 | MergeSort |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/sorts/MergeSort.java |
| 包名 | com.thealgorithms.sorts |
| 依赖项 | ['com.thealgorithms.sorts.SortUtils.less'] |
| 概述说明 | 归并排序算法实现，含排序与合并功能。 |

# 说明

该内容描述了实现归并排序算法的过程，涵盖了两个主要功能：排序和合并。归并排序是一种分治算法，通过将数组分成较小的子数组进行排序，然后将这些有序子数组合并成一个完整的有序数组。排序功能负责递归地将数组分解，直到每个子数组只有一个元素，此时它们自然有序。合并功能则负责将两个有序子数组合并成一个更大的有序数组，确保最终整个数组有序。整个过程强调分治策略和递归实现，确保算法的高效性和稳定性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| MergeSort | class | 实现归并排序算法，包括排序和合并功能。 |



## 类 MergeSort

|      |      |
|------|------|
| 访问范围 | None |
| 类型 | class |
| 名称 | MergeSort |
| 说明 | 实现归并排序算法，包括排序和合并功能。 |


### UML类图

```mermaid
classDiagram
    class SortAlgorithm {
        <<Interface>>
        +~T~[] sort(~T~[] unsorted) ~T~[]
    }

    class MergeSort {
        -Comparable[] aux
        +~T~[] sort(~T~[] unsorted) ~T~[]
        -~T~[] doSort(~T~[] arr, int left, int right) void
        -~T~[] merge(~T~[] arr, int left, int mid, int right) void
    }

    SortAlgorithm <|.. MergeSort : 实现
```

### 描述
该代码实现了一个归并排序算法。`MergeSort`类实现了`SortAlgorithm`接口，提供了`sort`方法来对数组进行排序。`doSort`方法递归地将数组分成两半进行排序，而`merge`方法则将两个有序数组合并成一个有序数组。整个过程通过递归和合并操作，最终将整个数组排序完成。


### 内部方法调用关系图

```mermaid
graph TD
    A["类MergeSort"]
    B["属性: Comparable[] aux"]
    C["方法: <T extends Comparable<T>> T[] sort(T[] unsorted)"]
    D["方法: <T extends Comparable<T>> void doSort(T[] arr, int left, int right)"]
    E["方法: <T extends Comparable<T>> void merge(T[] arr, int left, int mid, int right)"]
    F["步骤: aux = new Comparable[unsorted.length]"]
    G["步骤: doSort(unsorted, 0, unsorted.length - 1)"]
    H["步骤: return unsorted"]
    I["步骤: if (left < right)"]
    J["步骤: int mid = (left + right) >>> 1"]
    K["步骤: doSort(arr, left, mid)"]
    L["步骤: doSort(arr, mid + 1, right)"]
    M["步骤: merge(arr, left, mid, right)"]
    N["步骤: System.arraycopy(arr, left, aux, left, right + 1 - left)"]
    O["步骤: for (int k = left; k <= right; k++)"]
    P["步骤: if (j > right)"]
    Q["步骤: arr[k] = (T) aux[i++]"]
    R["步骤: else if (i > mid)"]
    S["步骤: arr[k] = (T) aux[j++]"]
    T["步骤: else if (less(aux[j], aux[i]))"]
    U["步骤: arr[k] = (T) aux[j++]"]
    V["步骤: else"]
    W["步骤: arr[k] = (T) aux[i++]"]

    A --> B
    A --> C
    A --> D
    A --> E
    C --> F
    C --> G
    C --> H
    D --> I
    I --> J
    I --> K
    I --> L
    I --> M
    E --> N
    E --> O
    O --> P
    P --> Q
    O --> R
    R --> S
    O --> T
    T --> U
    O --> V
    V --> W
```

这段代码实现了归并排序算法。`MergeSort`类包含一个辅助数组`aux`，用于在合并过程中存储临时数据。`sort`方法初始化`aux`并调用`doSort`方法进行递归排序。`doSort`方法将数组分成两部分，分别进行排序，然后调用`merge`方法将两部分合并。`merge`方法通过比较两部分元素的大小，将它们按顺序合并回原数组。整个过程通过递归和合并操作实现了数组的排序。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| aux | Comparable[] | 定义了一个私有的Comparable类型数组aux。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| merge | void | 泛型合并排序算法实现，将数组分成两部分并合并。 |
| sort | T[] | 重写sort方法，对未排序数组进行排序并返回。 |
| doSort | void | 私有方法doSort对数组进行递归排序，使用归并操作合并子数组。 |




