# 基础信息

|      |      |
|------|------|
| 名称 | EditDistance |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming/EditDistance.java |
| 包名 | com.thealgorithms.dynamicprogramming |
| 依赖项 | [] |
| 概述说明 | 计算字符串编辑距离，支持插入、删除和替换操作。 |

# 说明

计算两个字符串的编辑距离，衡量将一个字符串转换为另一个字符串所需的最少操作次数。支持的操作包括插入字符、删除字符和替换字符。编辑距离越小，表示两个字符串越相似。该算法常用于文本相似度比较、拼写检查和自然语言处理等领域。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| EditDistance | class | 计算两个字符串的编辑距离，支持插入、删除和替换操作。 |



## 类 EditDistance

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | EditDistance |
| 说明 | 计算两个字符串的编辑距离，支持插入、删除和替换操作。 |


### UML类图

```mermaid
classDiagram
    class EditDistance {
        +EditDistance()
        +int minDistance(String word1, String word2)
        +int editDistance(String s1, String s2)
        +int editDistance(String s1, String s2, int[][] storage)
    }
```

**描述：**  
`EditDistance` 类是一个工具类，用于计算两个字符串之间的编辑距离。它提供了两种方法：`minDistance` 和 `editDistance`。`minDistance` 使用动态规划来计算编辑距离，而 `editDistance` 则使用递归和记忆化存储来优化计算。该类是 `final` 的，表示不能被继承，并且构造函数是私有的，防止实例化。


### 内部方法调用关系图

```mermaid
graph TD
    A["类EditDistance"]
    B["构造方法: EditDistance()"]
    C["静态方法: int minDistance(String word1, String word2)"]
    D["静态方法: int editDistance(String s1, String s2)"]
    E["静态方法: int editDistance(String s1, String s2, int[][] storage)"]
    F["初始化dp数组: int[][] dp = new int[len1 + 1][len2 + 1]"]
    G["初始化dp[i][0] = i"]
    H["初始化dp[0][j] = j"]
    I["遍历word1和word2: for (int i = 0; i < len1; i++)"]
    J["遍历word2: for (int j = 0; j < len2; j++)"]
    K["比较字符: if (c1 == c2)"]
    L["更新dp[i + 1][j + 1] = dp[i][j]"]
    M["计算替换、插入、删除操作: int replace = dp[i][j] + 1"]
    N["计算插入操作: int insert = dp[i][j + 1] + 1"]
    O["计算删除操作: int delete = dp[i + 1][j] + 1"]
    P["取最小值: int min = Math.min(replace, insert)"]
    Q["取最小值: min = Math.min(delete, min)"]
    R["更新dp[i + 1][j + 1] = min"]
    S["返回结果: return dp[len1][len2]"]
    T["初始化storage数组: int[][] storage = new int[s1.length() + 1][s2.length() + 1]"]
    U["检查storage[m][n] > 0"]
    V["返回storage[m][n]"]
    W["检查m == 0"]
    X["返回storage[m][n] = n"]
    Y["检查n == 0"]
    Z["返回storage[m][n] = m"]
    AA["比较首字符: if (s1.charAt(0) == s2.charAt(0))"]
    AB["递归调用: storage[m][n] = editDistance(s1.substring(1), s2.substring(1), storage)"]
    AC["计算操作1: int op1 = editDistance(s1, s2.substring(1), storage)"]
    AD["计算操作2: int op2 = editDistance(s1.substring(1), s2, storage)"]
    AE["计算操作3: int op3 = editDistance(s1.substring(1), s2.substring(1), storage)"]
    AF["取最小值: storage[m][n] = 1 + Math.min(op1, Math.min(op2, op3))"]
    AG["返回storage[m][n]"]

    A --> B
    A --> C
    A --> D
    A --> E
    C --> F
    C --> G
    C --> H
    C --> I
    I --> J
    J --> K
    K --> L
    K --> M
    M --> N
    N --> O
    O --> P
    P --> Q
    Q --> R
    C --> S
    D --> T
    D --> E
    E --> U
    U --> V
    U --> W
    W --> X
    W --> Y
    Y --> Z
    E --> AA
    AA --> AB
    AA --> AC
    AC --> AD
    AD --> AE
    AE --> AF
    E --> AG
```

这段代码实现了计算两个字符串之间的编辑距离（Edit Distance），即从一个字符串转换到另一个字符串所需的最少操作次数。代码包含两个主要方法：`minDistance`和`editDistance`。`minDistance`使用动态规划的方法计算编辑距离，而`editDistance`则通过递归和备忘录（storage）来优化计算过程。流程图展示了各个方法的调用关系和内部逻辑，包括初始化、遍历、比较字符、计算操作次数以及返回结果等步骤。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| minDistance | int | 计算两字符串最小编辑距离的动态规划算法。 |
| editDistance | int | 计算字符串编辑距离，使用动态规划优化存储。 |
| editDistance | int | 计算字符串s1和s2的编辑距离，使用二维数组存储中间结果。 |




