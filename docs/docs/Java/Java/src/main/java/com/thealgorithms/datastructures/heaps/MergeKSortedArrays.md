# 基础信息

|      |      |
|------|------|
| 名称 | MergeKSortedArrays |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/datastructures/heaps/MergeKSortedArrays.java |
| 包名 | com.thealgorithms.datastructures.heaps |
| 依赖项 | ['java.util.Comparator', 'java.util.PriorityQueue'] |
| 概述说明 | 利用最小堆合并多个有序数组为单一有序数组。 |

# 说明

使用最小堆合并多个有序数组为单一有序数组的方法，首先将每个数组的第一个元素及其所属数组的索引存入最小堆。然后，从堆中取出最小元素，将其加入结果数组，并将该元素所属数组的下一个元素（如果存在）推入堆中。重复此过程，直到堆为空，最终得到合并后的单一有序数组。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| MergeKSortedArrays | class | 使用最小堆合并多个有序数组为单一有序数组。 |



## 类 MergeKSortedArrays

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | MergeKSortedArrays |
| 说明 | 使用最小堆合并多个有序数组为单一有序数组。 |


### UML类图

```mermaid
classDiagram
    class MergeKSortedArrays {
        +MergeKSortedArrays()
        +int[] mergeKArrays(int[][] arrays)
    }

    class PriorityQueue~int[]~ {
        +PriorityQueue(Comparator~int[]~ comparator)
        +boolean offer(int[] e)
        +int[] poll()
        +boolean isEmpty()
    }

    class Comparator~int[]~ {
        <<Interface>>
        +int compare(int[] a, int[] b)
    }

    MergeKSortedArrays --> PriorityQueue~int[]~ : 使用
    PriorityQueue~int[]~ --> Comparator~int[]~ : 依赖
```

### 描述
`MergeKSortedArrays` 类是一个工具类，用于合并多个已排序的数组。它使用 `PriorityQueue`（最小堆）来高效地合并这些数组。`PriorityQueue` 依赖于 `Comparator` 接口来比较数组中的元素。`mergeKArrays` 方法首先将每个数组的第一个元素添加到堆中，然后从堆中取出最小元素并添加到结果数组中，同时将下一个元素（如果存在）推入堆中，直到所有元素都被处理完毕。最终返回一个包含所有元素的排序数组。


### 内部方法调用关系图

```mermaid
graph TD
    A["类MergeKSortedArrays"]
    B["构造方法: MergeKSortedArrays()"]
    C["方法: int[] mergeKArrays(int[][] arrays)"]
    D["创建PriorityQueue<int[]> minHeap"]
    E["初始化int totalLength = 0"]
    F["遍历arrays, 将每个数组的第一个元素加入minHeap"]
    G["计算totalLength"]
    H["创建int[] result = new int[totalLength]"]
    I["初始化int index = 0"]
    J["while循环: minHeap不为空"]
    K["从minHeap中取出最小元素top"]
    L["将top[0]加入result数组"]
    M["检查top[2] + 1是否小于arrays[top[1]].length"]
    N["将下一个元素加入minHeap"]
    O["返回result数组"]

    A --> B
    A --> C
    C --> D
    C --> E
    C --> F
    F --> G
    C --> H
    C --> I
    C --> J
    J --> K
    K --> L
    L --> M
    M -->|是| N
    N --> J
    M -->|否| J
    J -->|结束| O
```

这段代码实现了一个合并多个已排序数组的功能。通过使用最小堆（PriorityQueue），代码首先将每个数组的第一个元素加入堆中，然后不断从堆中取出最小元素并加入结果数组，同时将该元素所在数组的下一个元素加入堆中，直到堆为空。最终返回的数组包含所有输入数组的元素，并按升序排列。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| mergeKArrays | int[] | 使用最小堆合并多个有序数组，返回合并后的有序数组。 |




