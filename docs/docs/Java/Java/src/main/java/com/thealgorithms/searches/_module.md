# 基础信息

|      |      |
|------|------|
| 名称 | searches |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/searches |
| 包名 | Java.src.main.java.com.thealgorithms.searches |
| 概述说明 | 多种搜索算法实现，包括斐波那契、二分、跳转、深度优先、广度优先等，适用于不同场景。 |

# 说明

## 概述

该代码模块主要实现了多种搜索算法，涵盖了从简单的线性搜索到复杂的图搜索算法。这些算法适用于不同的数据结构，包括一维数组、二维数组、树、图等。模块中的算法不仅支持基本的有序数组查找，还扩展到了无序数组、字符串匹配、矩阵搜索等场景。此外，模块还包含了一些高级算法，如并查集、蒙特卡洛树搜索、BM25倒排索引等，适用于更复杂的业务场景。

## 主要业务场景

1. **有序数组搜索**：模块提供了多种高效的有序数组搜索算法，包括二分查找、斐波那契搜索、插值搜索、指数搜索等。这些算法通过逐步缩小搜索范围，快速定位目标元素，适用于大规模数据集的查找任务。

2. **无序数组搜索**：模块还支持无序数组的搜索，如随机搜索和忽略排序顺序的二分查找。这些算法通过调整查找策略，能够在未排序的数组中有效定位目标元素，适用于无法预先排序或排序成本较高的数据集。

3. **二维数组搜索**：模块实现了多种二维数组搜索算法，如行列排序矩阵搜索、二维有序数组二分查找等。这些算法利用二维数组的有序性，通过逐步缩小搜索范围，快速定位目标值所在的行列索引。

4. **图与树搜索**：模块包含了深度优先搜索（DFS）和广度优先搜索（BFS）算法，适用于树或图数据结构的遍历与搜索。这些算法能够探索所有可能的路径，适用于寻找特定节点、检测环路或按层次遍历的场景。

5. **字符串匹配**：模块提供了KMP算法和Rabin-Karp算法，用于高效地进行字符串匹配。这些算法通过预处理模式串或计算哈希值，快速定位目标字符串中的匹配位置，适用于大规模文本匹配任务。

6. **高级搜索与优化**：模块还包含了一些高级算法，如并查集、蒙特卡洛树搜索、BM25倒排索引等。这些算法适用于复杂的业务场景，如处理不相交集合的合并与查询、游戏AI决策、电影信息检索等。

7. **特殊场景搜索**：模块还实现了一些特殊场景下的搜索算法，如计算数组旋转次数、查找第n大元素、计算平方根等。这些算法通过结合二分查找或其他优化策略，高效地解决特定问题。

总的来说，该代码模块提供了丰富的搜索算法实现，能够满足不同数据结构和业务场景下的搜索需求，具有较高的通用性和灵活性。


### 包内部结构视图

```mermaid
graph TD
    searches --> FibonacciSearch.java
    searches --> UpperBound.java
    searches --> JumpSearch.java
    searches --> DepthFirstSearch.java
    searches --> BreadthFirstSearch.java
    searches --> SortOrderAgnosticBinarySearch.java
    searches --> LowerBound.java
    searches --> BinarySearch2dArray.java
    searches --> UnionFind.java
    searches --> LinearSearch.java
    searches --> InterpolationSearch.java
    searches --> ExponentalSearch.java
    searches --> IterativeTernarySearch.java
    searches --> SearchInARowAndColWiseSortedMatrix.java
    searches --> IterativeBinarySearch.java
    searches --> RabinKarpAlgorithm.java
    searches --> BM25InvertedIndex.java
    searches --> HowManyTimesRotated.java
    searches --> MonteCarloTreeSearch.java
    searches --> QuickSelect.java
    searches --> RandomSearch.java
    searches --> TernarySearch.java
    searches --> SquareRootBinarySearch.java
    searches --> LinearSearchThread.java
    searches --> KMPSearch.java
    searches --> PerfectBinarySearch.java
    searches --> RowColumnWiseSorted2dArrayBinarySearch.java
    searches --> SaddlebackSearch.java
    searches --> RecursiveBinarySearch.java
    searches --> BinarySearch.java
    searches --> OrderAgnosticBinarySearch.java
```

该流程图展示了`searches`目录下的所有文件及其层级关系。每个文件都直接关联到`searches`目录，没有进一步的子目录结构。这些文件代表了各种搜索算法的实现，涵盖了从基本到高级的多种搜索技术。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [BinarySearch.java](BinarySearch.md) | file | BinarySearch类实现泛型二分查找，递归定位目标元素。 |
| [PerfectBinarySearch.java](PerfectBinarySearch.md) | file | 实现泛型二分查找，返回元素索引或-1。 |
| [LinearSearchThread.java](LinearSearchThread.md) | file | LinearSearchThread不可继承，Searcher继承Thread用于数组段搜索。 |
| [QuickSelect.java](QuickSelect.md) | file | QuickSelect类实现快速选择算法，返回列表中第n大元素，并处理异常。 |
| [RabinKarpAlgorithm.java](RabinKarpAlgorithm.md) | file | Rabin-Karp算法通过哈希值快速匹配字符串位置。 |
| [ExponentalSearch.java](ExponentalSearch.md) | file | 指数搜索用于在有序数组中查找元素索引，未找到返回-1。 |
| [BinarySearch2dArray.java](BinarySearch2dArray.md) | file | 二维有序数组二分查找目标值，返回行列索引，未找到返回[-1,-1]。 |
| [BreadthFirstSearch.java](BreadthFirstSearch.md) | file | 广度优先搜索类，查找指定节点并返回访问顺序。 |
| [JumpSearch.java](JumpSearch.md) | file | 跳转搜索算法用于在有序数组中快速查找目标元素。 |
| [SquareRootBinarySearch.java](SquareRootBinarySearch.md) | file | 二分查找算法计算平方根整数部分。 |
| [LowerBound.java](LowerBound.md) | file | LowerBound类实现二分搜索，查找有序数组中目标元素的下界位置。 |
| [OrderAgnosticBinarySearch.java](OrderAgnosticBinarySearch.md) | file | 实现无序数组二分查找，支持升序和降序。 |
| [RecursiveBinarySearch.java](RecursiveBinarySearch.md) | file | 抽象类定义泛型查找算法，子类实现递归二分查找。 |
| [SaddlebackSearch.java](SaddlebackSearch.md) | file | SaddlebackSearch类通过递归查找有序二维数组中元素的索引。 |
| [RowColumnWiseSorted2dArrayBinarySearch.java](RowColumnWiseSorted2dArrayBinarySearch.md) | file | 二维数组行列排序后应用二分查找算法。 |
| [KMPSearch.java](KMPSearch.md) | file | KMP算法通过预处理模式串实现高效字符串匹配并返回匹配索引。 |
| [TernarySearch.java](TernarySearch.md) | file | TernarySearch类实现二分查找，返回有序数组中元素索引或-1。 |
| [RandomSearch.java](RandomSearch.md) | file | 随机搜索算法通过随机索引查找数组元素，未找到返回-1。 |
| [MonteCarloTreeSearch.java](MonteCarloTreeSearch.md) | file | MonteCarloTreeSearch通过模拟随机游戏选择最优节点。 |
| [HowManyTimesRotated.java](HowManyTimesRotated.md) | file | Java程序通过二分查找确定数组旋转次数。 |
| [BM25InvertedIndex.java](BM25InvertedIndex.md) | file | 电影类含ID、名称、评分、年份和内容，提供单词获取。SearchResult类含ID和BM25评分，支持构造、获取、比较和哈希。BM25索引类存储电影信息，支持添加和搜索。 |
| [IterativeBinarySearch.java](IterativeBinarySearch.md) | file | 迭代二分查找，返回目标索引或-1。 |
| [SearchInARowAndColWiseSortedMatrix.java](SearchInARowAndColWiseSortedMatrix.md) | file | 行列排序矩阵中搜索指定值的高效算法。 |
| [IterativeTernarySearch.java](IterativeTernarySearch.md) | file | 迭代三分搜索算法用于查找数组中的指定元素。 |
| [InterpolationSearch.java](InterpolationSearch.md) | file | 插值搜索在有序数组中查找值，未找到返回-1。 |
| [LinearSearch.java](LinearSearch.md) | file | 线性搜索遍历数组查找目标值，返回位置或未找到时返回-1。 |
| [UnionFind.java](UnionFind.md) | file | 并查集支持初始化、查找、合并和计数操作。 |
| [SortOrderAgnosticBinarySearch.java](SortOrderAgnosticBinarySearch.md) | file | 忽略顺序的二分查找实现。 |
| [DepthFirstSearch.java](DepthFirstSearch.md) | file | 深度优先搜索类，支持递归遍历并记录路径。 |
| [UpperBound.java](UpperBound.md) | file | UpperBound类通过二分查找算法在有序数组中确定目标值的上界位置。 |
| [FibonacciSearch.java](FibonacciSearch.md) | file | FibonacciSearch类用斐波那契数列在有序数组中查找元素，返回索引或-1。 |


