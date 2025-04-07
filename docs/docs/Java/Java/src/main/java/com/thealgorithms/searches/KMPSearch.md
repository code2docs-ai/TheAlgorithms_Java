# 基础信息

|      |      |
|------|------|
| 名称 | KMPSearch |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/searches/KMPSearch.java |
| 包名 | com.thealgorithms.searches |
| 依赖项 | [] |
| 概述说明 | KMP算法通过预处理模式串实现高效字符串匹配并返回匹配索引。 |

# 说明

KMP算法是一种高效的字符串匹配算法，通过预处理模式串，构建部分匹配表，利用该表在匹配过程中跳过不必要的字符比较，从而提高匹配效率。算法最终返回模式串在目标字符串中的匹配索引。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| KMPSearch | class | KMP算法实现字符串匹配，预处理模式串并返回匹配索引。 |



## 类 KMPSearch

|      |      |
|------|------|
| 访问范围 | None |
| 类型 | class |
| 名称 | KMPSearch |
| 说明 | KMP算法实现字符串匹配，预处理模式串并返回匹配索引。 |


### UML类图

```mermaid
classDiagram
    class KMPSearch {
        +int kmpSearch(String pat, String txt)
        -void computeLPSArray(String pat, int m, int[] lps)
    }
```

**描述：**  
`KMPSearch` 类实现了KMP（Knuth-Morris-Pratt）字符串搜索算法，用于在文本中查找模式字符串的位置。该类包含两个方法：`kmpSearch` 用于执行搜索并返回模式在文本中的起始索引，`computeLPSArray` 用于预处理模式字符串，生成最长前缀后缀数组（LPS数组）。KMP算法通过利用LPS数组避免不必要的字符比较，从而提高搜索效率。


### 内部方法调用关系图

```mermaid
graph TD
    A["类KMPSearch"]
    B["方法: int kmpSearch(String pat, String txt)"]
    C["方法: void computeLPSArray(String pat, int m, int[] lps)"]
    D["初始化变量: int m = pat.length(), int n = txt.length()"]
    E["创建数组: int[] lps = new int[m]"]
    F["调用computeLPSArray(pat, m, lps)"]
    G["初始化变量: int i = 0, int j = 0"]
    H["循环: while ((n - i) >= (m - j))"]
    I["判断: if (pat.charAt(j) == txt.charAt(i))"]
    J["增加索引: j++, i++"]
    K["判断: if (j == m)"]
    L["输出: System.out.println('Found pattern at index ' + (i - j))"]
    M["返回索引: return (i - j)"]
    N["判断: else if (i < n && pat.charAt(j) != txt.charAt(i))"]
    O["判断: if (j != 0)"]
    P["更新索引: j = lps[j - 1]"]
    Q["增加索引: i = i + 1"]
    R["输出: System.out.println('No pattern found')"]
    S["返回: return -1"]
    T["循环: while (i < m)"]
    U["判断: if (pat.charAt(i) == pat.charAt(len))"]
    V["增加长度: len++, lps[i] = len, i++"]
    W["判断: else if (len != 0)"]
    X["更新长度: len = lps[len - 1]"]
    Y["更新数组: lps[i] = len, i++"]

    A --> B
    A --> C
    B --> D
    B --> E
    B --> F
    B --> G
    B --> H
    H --> I
    I --> J
    I --> K
    K --> L
    K --> M
    I --> N
    N --> O
    O --> P
    O --> Q
    H --> R
    R --> S
    C --> T
    T --> U
    U --> V
    U --> W
    W --> X
    W --> Y
```

这段代码实现了KMP（Knuth-Morris-Pratt）字符串匹配算法。`kmpSearch`方法用于在文本中查找模式字符串的位置，`computeLPSArray`方法用于预处理模式字符串，生成最长前缀后缀数组（LPS）。流程图展示了方法的调用顺序和逻辑判断过程，清晰地展示了算法的执行流程。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| kmpSearch | int | KMP算法实现字符串匹配，返回匹配位置或-1。 |
| computeLPSArray | void | 计算模式串的最长前缀后缀数组。 |




