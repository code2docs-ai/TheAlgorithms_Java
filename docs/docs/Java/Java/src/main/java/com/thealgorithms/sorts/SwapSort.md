# 基础信息

|      |      |
|------|------|
| 名称 | SwapSort |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/sorts/SwapSort.java |
| 包名 | com.thealgorithms.sorts |
| 依赖项 | [] |
| 概述说明 | SwapSort通过交换较小元素实现数组排序。 |

# 说明

SwapSort是一种基于交换操作的排序算法，其主要思想是通过不断交换数组中较小的元素，逐步将数组中的元素按升序排列。该算法通过遍历数组，每次比较相邻元素的大小，如果发现前一个元素大于后一个元素，则进行交换。这一过程会重复进行，直到整个数组中的元素都按照从小到大的顺序排列。SwapSort的核心在于通过简单的交换操作实现排序，其时间复杂度较高，适用于小规模数据的排序场景。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| SwapSort | class | SwapSort实现排序算法，通过交换较小元素完成数组排序。 |



## 类 SwapSort

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | SwapSort |
| 说明 | SwapSort实现排序算法，通过交换较小元素完成数组排序。 |


### UML类图

```mermaid
classDiagram
    class SwapSort {
        +sort(T~Comparable~[] array) T~Comparable~[]
        -getSmallerElementCount(T~Comparable~[] array, int index) int
    }

    class SortUtils {
        <<Interface>>
        +swap(T[] array, int i, int j) void
        +less(T~Comparable~ a, T~Comparable~ b) boolean
    }

    SwapSort --> SortUtils : 依赖
```

**描述：**  
`SwapSort`类实现了`SortAlgorithm`接口，提供了一个泛型排序方法`sort`，用于对实现了`Comparable`接口的数组进行排序。它通过`getSmallerElementCount`方法计算当前元素后比它小的元素数量，并根据结果决定是否交换元素位置。`SortUtils`接口提供了`swap`和`less`两个静态方法，分别用于交换数组元素和比较两个元素的大小。`SwapSort`类依赖于`SortUtils`接口来完成排序操作。


### 内部方法调用关系图

```mermaid
graph TD
    A["类SwapSort"]
    B["方法: <T extends Comparable<T>> T[] sort(T[] array)"]
    C["变量: int index = 0"]
    D["循环: while (index < array.length - 1)"]
    E["方法调用: this.getSmallerElementCount(array, index)"]
    F["条件判断: if (amountSmallerElements > 0)"]
    G["方法调用: SortUtils.swap(array, index, index + amountSmallerElements)"]
    H["操作: index++"]
    I["返回: return array"]
    J["方法: <T extends Comparable<T>> int getSmallerElementCount(final T[] array, final int index)"]
    K["变量: int counter = 0"]
    L["循环: for (int i = index + 1; i < array.length; i++)"]
    M["条件判断: if (SortUtils.less(array[i], array[index]))"]
    N["操作: counter++"]
    O["返回: return counter"]

    A --> B
    B --> C
    B --> D
    D --> E
    E --> F
    F -->|是| G
    F -->|否| H
    G --> D
    H --> D
    D -->|循环结束| I
    B --> J
    J --> K
    J --> L
    L --> M
    M -->|是| N
    N --> L
    M -->|否| L
    L -->|循环结束| O
```

这段代码实现了一个名为`SwapSort`的排序算法。该算法通过比较数组中的元素，计算当前元素之后比它小的元素数量，并根据结果进行交换操作，直到数组排序完成。流程图展示了`sort`方法和`getSmallerElementCount`方法的内部逻辑，包括循环、条件判断和方法的调用关系。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| sort | T[] | 该方法通过比较和交换元素对数组进行排序。 |
| getSmallerElementCount | int | 计算数组中指定索引后小于该元素的个数。 |




