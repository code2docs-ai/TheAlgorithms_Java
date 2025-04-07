# 基础信息

|      |      |
|------|------|
| 名称 | UniquePaths |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming/UniquePaths.java |
| 包名 | com.thealgorithms.dynamicprogramming |
| 依赖项 | ['java.util.Arrays'] |
| 概述说明 | UniquePaths类提供两种动态规划方法计算网格路径数，1D数组空间低，2D数组直观但空间高。 |

# 说明

UniquePaths类提供了两种动态规划方法来计算网格中的唯一路径数。第一种方法使用一维数组，具有较低的空间复杂度，适合优化内存使用。第二种方法使用二维数组，虽然更加直观，但空间复杂度较高，适合理解算法逻辑。两种方法各有优劣，用户可根据具体需求选择合适的方式。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| UniquePaths | class | UniquePaths类提供两种动态规划方法计算网格唯一路径数，1D数组空间复杂度低，2D数组直观但空间复杂度高。 |



## 类 UniquePaths

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | UniquePaths |
| 说明 | UniquePaths类提供两种动态规划方法计算网格唯一路径数，1D数组空间复杂度低，2D数组直观但空间复杂度高。 |


### UML类图

```mermaid
classDiagram
    class UniquePaths {
        -UniquePaths()
        +uniquePaths(int m, int n) int
        +uniquePaths2(int m, int n) int
    }

    class Arrays {
        <<Interface>>
        +fill(int[] a, int val) void
    }

    class Math {
        <<Interface>>
        +addExact(int x, int y) int
    }

    UniquePaths --> Arrays : 依赖
    UniquePaths --> Math : 依赖
```

**描述：**  
`UniquePaths` 类提供了两种计算网格中唯一路径数量的方法：`uniquePaths` 和 `uniquePaths2`。`uniquePaths` 使用一维动态规划数组，空间复杂度为 `O(min(n,m))`，而 `uniquePaths2` 使用二维动态规划数组，空间复杂度为 `O(n*m)`。两种方法都通过递归和动态规划来更新路径数量，最终返回从起点到终点的唯一路径数。`UniquePaths` 类依赖于 `Arrays` 和 `Math` 类来执行数组初始化和加法操作。


### 内部方法调用关系图

```mermaid
graph TD
    A["类UniquePaths"]
    B["构造方法: UniquePaths()"]
    C["方法: uniquePaths(int m, int n)"]
    D["方法: uniquePaths2(int m, int n)"]
    E["判断: if (m > n)"]
    F["递归调用: uniquePaths(n, m)"]
    G["创建数组: int[] dp = new int[n]"]
    H["初始化数组: Arrays.fill(dp, 1)"]
    I["循环: for (int i = 1; i < m; i++)"]
    J["循环: for (int j = 1; j < n; j++)"]
    K["更新路径数: dp[j] = Math.addExact(dp[j], dp[j - 1])"]
    L["返回结果: return dp[n - 1]"]
    M["创建二维数组: int[][] dp = new int[m][n]"]
    N["初始化第一列: dp[i][0] = 1"]
    O["初始化第一行: dp[0][j] = 1"]
    P["循环: for (int i = 1; i < m; i++)"]
    Q["循环: for (int j = 1; j < n; j++)"]
    R["更新路径数: dp[i][j] = Math.addExact(dp[i - 1][j], dp[i][j - 1])"]
    S["返回结果: return dp[m - 1][n - 1]"]

    A --> B
    A --> C
    A --> D
    C --> E
    E -->|是| F
    E -->|否| G
    G --> H
    H --> I
    I --> J
    J --> K
    K --> J
    J --> I
    I --> L
    D --> M
    M --> N
    M --> O
    N --> P
    O --> P
    P --> Q
    Q --> R
    R --> Q
    Q --> P
    P --> S
```

这段代码实现了两个方法来计算网格中的唯一路径数。`uniquePaths`方法使用一维动态规划数组，通过递归调用来处理行数大于列数的情况，并最终返回结果。`uniquePaths2`方法使用二维动态规划数组，初始化第一行和第一列后，通过双重循环更新每个单元格的路径数，最终返回右下角单元格的值。两种方法的时间复杂度均为O(n*m)，但空间复杂度分别为O(min(n,m))和O(n*m)。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| uniquePaths2 | int | 计算二维网格从左上到右下的唯一路径数，使用动态规划初始化边界并逐格累加。 |
| uniquePaths | int | 计算m×n网格中从左上角到右下角的唯一路径数，使用动态规划优化空间复杂度。 |




