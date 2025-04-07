# 基础信息

|      |      |
|------|------|
| 名称 | LongestPalindromicSubsequence |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming/LongestPalindromicSubsequence.java |
| 包名 | com.thealgorithms.dynamicprogramming |
| 依赖项 | [] |
| 概述说明 | Java类递归计算字符串最长回文子序列。 |

# 说明

该内容描述了一个Java类，其功能是计算字符串的最长回文子序列。实现方法采用递归技术，通过递归调用来逐步分解问题并找到最长回文子序列。递归方法在处理字符串时，通过比较字符并逐步缩小问题规模，最终确定最长回文子序列的长度。这种方法虽然直观，但在处理较长字符串时可能会面临性能挑战。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| LongestPalindromicSubsequence | class | Java类计算字符串的最长回文子序列，通过递归方法实现。 |



## 类 LongestPalindromicSubsequence

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | LongestPalindromicSubsequence |
| 说明 | Java类计算字符串的最长回文子序列，通过递归方法实现。 |


### UML类图

```mermaid
classDiagram
    class LongestPalindromicSubsequence {
        +LongestPalindromicSubsequence()
        +static void main(String[] args)
        +static String lps(String original) throws IllegalArgumentException
        -static String recursiveLPS(String original, String reverse)
    }
```

### 描述
`LongestPalindromicSubsequence` 类是一个用于查找字符串中最长回文子序列的工具类。它包含一个私有的构造函数以防止实例化，一个 `main` 方法用于测试，以及两个静态方法 `lps` 和 `recursiveLPS`。`lps` 方法接受一个字符串并返回其最长回文子序列，而 `recursiveLPS` 是一个递归辅助方法，用于比较原始字符串和其反转字符串，逐步构建最长回文子序列。


### 内部方法调用关系图

```mermaid
graph TD
    A["类LongestPalindromicSubsequence"]
    B["构造方法: LongestPalindromicSubsequence()"]
    C["main方法: main(String[] args)"]
    D["变量: String a = 'BBABCBCAB'"]
    E["变量: String b = 'BABCBAB'"]
    F["方法调用: String aLPS = lps(a)"]
    G["方法调用: String bLPS = lps(b)"]
    H["输出: System.out.println(a + ' => ' + aLPS)"]
    I["输出: System.out.println(b + ' => ' + bLPS)"]
    J["方法: String lps(String original)"]
    K["变量: StringBuilder reverse = new StringBuilder(original)"]
    L["方法调用: reverse = reverse.reverse()"]
    M["方法调用: return recursiveLPS(original, reverse.toString())"]
    N["方法: String recursiveLPS(String original, String reverse)"]
    O["变量: String bestResult = ''"]
    P["条件判断: original.length() == 0 || reverse.length() == 0"]
    Q["赋值: bestResult = ''"]
    R["条件判断: original.charAt(original.length() - 1) == reverse.charAt(reverse.length() - 1)"]
    S["方法调用: String bestSubResult = recursiveLPS(original.substring(0, original.length() - 1), reverse.substring(0, reverse.length() - 1))"]
    T["赋值: bestResult = reverse.charAt(reverse.length() - 1) + bestSubResult"]
    U["方法调用: String bestSubResult1 = recursiveLPS(original, reverse.substring(0, reverse.length() - 1))"]
    V["方法调用: String bestSubResult2 = recursiveLPS(original.substring(0, original.length() - 1), reverse)"]
    W["条件判断: bestSubResult1.length() > bestSubResult2.length()"]
    X["赋值: bestResult = bestSubResult1"]
    Y["赋值: bestResult = bestSubResult2"]
    Z["返回: return bestResult"]

    A --> B
    A --> C
    C --> D
    C --> E
    C --> F
    C --> G
    C --> H
    C --> I
    F --> J
    G --> J
    J --> K
    J --> L
    J --> M
    M --> N
    N --> O
    N --> P
    P --> Q
    P --> R
    R --> S
    R --> T
    R --> U
    R --> V
    U --> W
    V --> W
    W --> X
    W --> Y
    N --> Z
```

这段代码用于寻找给定字符串的最长回文子序列（Longest Palindromic Subsequence, LPS）。通过递归方法，代码比较字符串及其反转字符串的字符，逐步构建最长回文子序列。流程图展示了从主方法到递归调用的完整流程，包括字符串的反转、字符比较以及结果的选择与返回。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| main | void | Java代码计算字符串的最长回文子序列并输出结果。 |
| recursiveLPS | String | 递归查找最长回文子串，匹配字符则递归，否则取较长结果。 |
| lps | String | 静态方法lps反转字符串并递归查找最长回文子串。 |




