# 基础信息

|      |      |
|------|------|
| 名称 | UniqueSubsequencesCount |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming/UniqueSubsequencesCount.java |
| 包名 | com.thealgorithms.dynamicprogramming |
| 依赖项 | ['java.util.Arrays', 'java.util.HashSet', 'java.util.Set'] |
| 概述说明 | UniqueSubsequencesCount类利用动态规划递归计算字符串唯一子序列数。 |

# 说明

UniqueSubsequencesCount类采用动态规划方法，通过递归机制计算给定字符串中所有唯一子序列的数量。该方法利用动态规划的特性，逐步构建子问题的解，从而高效地计算出最终结果。通过递归调用，系统能够处理字符串的各个子串，确保每个可能的子序列都被考虑并计数，最终得到唯一子序列的总数。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| UniqueSubsequencesCount | class | UniqueSubsequencesCount类通过动态规划递归计算字符串的唯一子序列数。 |



## 类 UniqueSubsequencesCount

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | UniqueSubsequencesCount |
| 说明 | UniqueSubsequencesCount类通过动态规划递归计算字符串的唯一子序列数。 |


### UML类图

```mermaid
classDiagram
    class UniqueSubsequencesCount {
        <<final>>
        +UniqueSubsequencesCount() throws UnsupportedOperationException
        +int countSubseq(String str)
        +int countSubsequences(String st, int idx, int[] dp)
    }

    class Arrays {
        <<final>>
        +void fill(int[] a, int val)
    }

    class HashSet~T~ {
        <<Interface>>
        +boolean add(T e)
        +boolean contains(Object o)
    }

    class Set~T~ {
        <<Interface>>
    }

    UniqueSubsequencesCount --> Arrays : 依赖
    UniqueSubsequencesCount --> HashSet~Character~ : 依赖
    HashSet~Character~ --|> Set~Character~
```

这段代码定义了一个工具类 `UniqueSubsequencesCount`，用于计算字符串中唯一子序列的数量。该类包含两个静态方法：`countSubseq` 和 `countSubsequences`，前者初始化动态规划数组并调用后者进行递归计算。`countSubsequences` 方法使用 `HashSet` 来避免重复字符，并通过动态规划数组 `dp` 进行结果缓存，以提高效率。`Arrays` 类用于初始化数组，`HashSet` 实现了 `Set` 接口，用于存储和检查字符。


### 内部方法调用关系图

```mermaid
graph TD
    A["类UniqueSubsequencesCount"]
    B["构造方法: UniqueSubsequencesCount()"]
    C["抛出异常: UnsupportedOperationException"]
    D["静态方法: countSubseq(String str)"]
    E["初始化DP数组: int[] dp = new int[str.length() + 1]"]
    F["填充DP数组: Arrays.fill(dp, -1)"]
    G["调用递归方法: countSubsequences(st, idx, dp)"]
    H["静态方法: countSubsequences(String st, int idx, int[] dp)"]
    I["基础条件: if (idx >= st.length())"]
    J["返回0"]
    K["检查DP数组: if (dp[idx] != -1)"]
    L["返回dp[idx]"]
    M["初始化Set: Set<Character> set = new HashSet<>()"]
    N["初始化res: int res = 0"]
    O["循环: for (int j = idx; j < st.length(); j++)"]
    P["检查字符是否在Set中: if (set.contains(st.charAt(j)))"]
    Q["跳过当前字符: continue"]
    R["添加字符到Set: set.add(st.charAt(j))"]
    S["计算子序列: res = 1 + countSubsequences(st, j + 1, dp) + res"]
    T["存储结果到DP数组: dp[idx] = res"]
    U["返回dp[idx]"]

    A --> B
    B --> C
    A --> D
    D --> E
    D --> F
    D --> G
    G --> H
    H --> I
    I --> J
    H --> K
    K --> L
    H --> M
    H --> N
    H --> O
    O --> P
    P --> Q
    O --> R
    O --> S
    H --> T
    H --> U
```

这段代码定义了一个名为 `UniqueSubsequencesCount` 的工具类，用于计算给定字符串中唯一子序列的数量。代码通过动态规划和递归的方法来避免重复计算，并利用 `HashSet` 来确保子序列中的字符唯一。流程图展示了从初始化到递归计算的完整流程，包括基础条件、DP数组的使用以及字符去重的逻辑。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| countSubseq | int | 静态方法countSubseq使用动态规划计算字符串子序列数量。 |
| countSubsequences | int | 动态规划计算字符串不重复子序列数量。 |




