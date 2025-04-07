# 基础信息

|      |      |
|------|------|
| 名称 | MinimumPathSum |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming/MinimumPathSum.java |
| 包名 | com.thealgorithms.dynamicprogramming |
| 依赖项 | [] |
| 概述说明 | 计算二维网格左上到右下的最小路径和。 |

# 说明

该问题要求计算在一个二维网格中，从左上角到右下角的最小路径和。具体来说，网格中的每个单元格包含一个数值，路径只能向右或向下移动。目标是找到一条路径，使得路径上所有单元格的数值之和最小。这个问题通常通过动态规划方法来解决，通过逐步计算每个单元格的最小路径和，最终得到从起点到终点的最小路径和。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| MinimumPathSum | class | 计算二维网格中从左上到右下的最小路径和。 |



## 类 MinimumPathSum

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | MinimumPathSum |
| 说明 | 计算二维网格中从左上到右下的最小路径和。 |


### UML类图

```mermaid
classDiagram
    class MinimumPathSum {
        -MinimumPathSum()
        +int minimumPathSum(int[][] grid)
    }
```

**描述：**  
`MinimumPathSum` 是一个工具类，用于计算二维网格中从左上角到右下角的最小路径和。它使用动态规划（DP）来优化计算过程，通过初始化一个一维数组 `dp` 来存储每一行的最小路径和，并逐步更新该数组，最终返回右下角的最小路径和。该类是 `final` 的，且构造函数是私有的，确保它不能被实例化或继承。


### 内部方法调用关系图

```mermaid
graph TD
    A["类MinimumPathSum"]
    B["构造方法: MinimumPathSum()"]
    C["静态方法: minimumPathSum(int[][] grid)"]
    D["获取行数: numRows = grid.length"]
    E["获取列数: numCols = grid[0].length"]
    F["检查列数是否为0: if (numCols == 0)"]
    G["返回0: return 0"]
    H["初始化dp数组: int[] dp = new int[numCols]"]
    I["初始化dp[0]: dp[0] = grid[0][0]"]
    J["计算第一行的最小路径和: for (int col = 1; col < numCols; col++)"]
    K["更新dp[col]: dp[col] = dp[col - 1] + grid[0][col]"]
    L["计算剩余行的最小路径和: for (int row = 1; row < numRows; row++)"]
    M["更新第一列的最小路径和: dp[0] += grid[row][0]"]
    N["计算每列的最小路径和: for (int col = 1; col < numCols; col++)"]
    O["选择最小路径和并更新: dp[col] = Math.min(dp[col - 1], dp[col]) + grid[row][col]"]
    P["返回最后单元格的最小路径和: return dp[numCols - 1]"]

    A --> B
    A -.-> C
    C --> D
    C --> E
    C --> F
    F --> G
    C --> H
    C --> I
    C --> J
    J --> K
    C --> L
    L --> M
    L --> N
    N --> O
    C --> P
```

这段代码实现了一个计算二维网格中从左上角到右下角的最小路径和的算法。首先，代码获取网格的行数和列数，并检查列数是否为0。接着，初始化一个dp数组用于存储每列的最小路径和。然后，分别计算第一行和剩余行的最小路径和，最终返回右下角单元格的最小路径和。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| minimumPathSum | int | 计算二维网格从左上到右下的最小路径和。 |




