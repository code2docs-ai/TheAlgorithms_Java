# 基础信息

|      |      |
|------|------|
| 名称 | IntrospectiveSort |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/sorts/IntrospectiveSort.java |
| 包名 | com.thealgorithms.sorts |
| 依赖项 | [] |
| 概述说明 | 内省排序融合快排、堆排和插排，通过递归深度优化排序策略。 |

# 说明

内省排序是一种结合了快速排序、堆排序和插入排序的混合排序算法。它通过递归深度控制来动态选择最适合的排序策略，以提高整体排序效率。具体来说，内省排序在递归深度较小时使用快速排序，以利用其平均时间复杂度较低的优势；当递归深度达到一定阈值时，切换到堆排序，以避免快速排序在最坏情况下的性能退化；对于小规模数据，则使用插入排序，因为其在处理小数据量时具有较高的效率。这种策略使得内省排序在各种情况下都能保持良好的性能。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| IntrospectiveSort | class | 内省排序结合快速排序、堆排序和插入排序，递归深度控制排序策略。 |



## 类 IntrospectiveSort

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | IntrospectiveSort |
| 说明 | 内省排序结合快速排序、堆排序和插入排序，递归深度控制排序策略。 |


### UML类图

```mermaid
classDiagram
    class IntrospectiveSort {
        -int INSERTION_SORT_THRESHOLD
        +~T extends Comparable~T~[] sort(T[] array)
        -~T extends Comparable~T~ void introspectiveSort(T[] array, int low, int high, int depth)
        -~T extends Comparable~T~ int partition(T[] array, int low, int high)
        -~T extends Comparable~T~ void insertionSort(T[] array, int low, int high)
        -~T extends Comparable~T~ void heapSort(T[] array, int low, int high)
        -~T extends Comparable~T~ void heapify(T[] array, int i, int n, int low)
    }

    class SortUtils {
        +~T~ void swap(T[] array, int i, int j)
    }

    IntrospectiveSort --> SortUtils : 依赖
```

### 描述
`IntrospectiveSort` 类实现了自省排序算法，结合了快速排序、堆排序和插入排序的优点。该类包含多个私有方法，如 `introspectiveSort`、`partition`、`insertionSort`、`heapSort` 和 `heapify`，用于处理不同规模的数组排序。`SortUtils` 类提供了一个静态方法 `swap`，用于交换数组中的元素。`IntrospectiveSort` 类依赖于 `SortUtils` 类来实现元素交换操作。


### 内部方法调用关系图

```mermaid
graph TD
    A["类IntrospectiveSort"]
    B["常量: INSERTION_SORT_THRESHOLD = 16"]
    C["方法: <T extends Comparable<T>> T[] sort(T[] array)"]
    D["方法: <T extends Comparable<T>> void introspectiveSort(T[] array, int low, int high, int depth)"]
    E["方法: <T extends Comparable<T>> int partition(T[] array, int low, int high)"]
    F["方法: <T extends Comparable<T>> void insertionSort(T[] array, int low, int high)"]
    G["方法: <T extends Comparable<T>> void heapSort(T[] array, int low, int high)"]
    H["方法: <T extends Comparable<T>> void heapify(T[] array, int i, int n, int low)"]
    I["条件: array == null || array.length <= 1"]
    J["计算: depth = 2 * (int) (Math.log(array.length) / Math.log(2))"]
    K["调用: introspectiveSort(array, 0, array.length - 1, depth)"]
    L["条件: high - low > INSERTION_SORT_THRESHOLD"]
    M["条件: depth == 0"]
    N["调用: heapSort(array, low, high)"]
    O["调用: partition(array, low, high)"]
    P["调用: introspectiveSort(array, pivotIndex + 1, high, depth - 1)"]
    Q["更新: high = pivotIndex - 1"]
    R["调用: insertionSort(array, low, high)"]
    S["计算: pivotIndex = low + (int) (Math.random() * (high - low + 1))"]
    T["调用: SortUtils.swap(array, pivotIndex, high)"]
    U["赋值: pivot = array[high]"]
    V["循环: for (int j = low; j < high; j++)"]
    W["条件: array[j].compareTo(pivot) <= 0"]
    X["调用: SortUtils.swap(array, i, j)"]
    Y["调用: SortUtils.swap(array, i + 1, high)"]
    Z["返回: i + 1"]
    AA["循环: for (int i = low + 1; i <= high; i++)"]
    AB["赋值: key = array[i]"]
    AC["循环: while (j >= low && array[j].compareTo(key) > 0)"]
    AD["赋值: array[j + 1] = array[j]"]
    AE["赋值: array[j + 1] = key"]
    AF["计算: n = high - low + 1"]
    AG["循环: for (int i = (n / 2) - 1; i >= 0; i--)"]
    AH["调用: heapify(array, i, n, low)"]
    AI["循环: for (int i = high; i > low; i--)"]
    AJ["调用: SortUtils.swap(array, low, i)"]
    AK["调用: heapify(array, 0, i - low, low)"]
    AL["计算: left = 2 * i + 1"]
    AM["计算: right = 2 * i + 2"]
    AN["赋值: largest = i"]
    AO["条件: left < n && array[low + left].compareTo(array[low + largest]) > 0"]
    AP["赋值: largest = left"]
    AQ["条件: right < n && array[low + right].compareTo(array[low + largest]) > 0"]
    AR["赋值: largest = right"]
    AS["条件: largest != i"]
    AT["调用: SortUtils.swap(array, low + i, low + largest)"]
    AU["调用: heapify(array, largest, n, low)"]

    A --> B
    A --> C
    C --> I
    I -->|true| K
    I -->|false| J
    J --> K
    K --> D
    D --> L
    L -->|true| M
    M -->|true| N
    M -->|false| O
    O --> P
    P --> Q
    Q --> L
    L -->|false| R
    O --> S
    S --> T
    T --> U
    U --> V
    V --> W
    W -->|true| X
    X --> V
    W -->|false| V
    V --> Y
    Y --> Z
    R --> AA
    AA --> AB
    AB --> AC
    AC -->|true| AD
    AD --> AC
    AC -->|false| AE
    AE --> AA
    N --> AF
    AF --> AG
    AG --> AH
    AH --> AG
    AG --> AI
    AI --> AJ
    AJ --> AK
    AK --> AI
    AH --> AL
    AL --> AM
    AM --> AN
    AN --> AO
    AO -->|true| AP
    AP --> AQ
    AO -->|false| AQ
    AQ -->|true| AR
    AR --> AS
    AQ -->|false| AS
    AS -->|true| AT
    AT --> AU
    AU --> AS
    AS -->|false| AU
```

这段代码实现了自省排序（Introspective Sort），它结合了快速排序、堆排序和插入排序的优点。首先，代码检查数组是否为空或长度小于等于1，如果是则直接返回。否则，计算递归深度并调用`introspectiveSort`方法。在`introspectiveSort`中，根据子数组长度和递归深度决定使用堆排序、快速排序还是插入排序。快速排序通过`partition`方法划分数组，堆排序通过`heapSort`和`heapify`方法维护堆性质，插入排序通过`insertionSort`方法对小数组进行排序。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| INSERTION_SORT_THRESHOLD = 16 | int | 插入排序阈值为16。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| heapSort | void | 堆排序算法，构建堆并逐步排序数组元素。 |
| partition | int | 随机选择基准元素，进行数组分区并返回分区点。 |
| insertionSort | void | 插入排序实现，对数组指定范围进行升序排列。 |
| heapify | void | 堆排序中调整堆结构的私有方法，确保最大元素位于堆顶。 |
| introspectiveSort | void | 内省排序算法结合堆排序、快速排序和插入排序，递归处理数组。 |
| sort | T[] | 重写sort方法，处理空或单元素数组，计算深度并调用内省排序。 |




