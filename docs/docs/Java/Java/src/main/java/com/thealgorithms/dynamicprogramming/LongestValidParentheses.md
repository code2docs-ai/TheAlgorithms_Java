# 基础信息

|      |      |
|------|------|
| 名称 | LongestValidParentheses |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming/LongestValidParentheses.java |
| 包名 | com.thealgorithms.dynamicprogramming |
| 依赖项 | [] |
| 概述说明 | 计算字符串中最长有效括号子串的长度。 |

# 说明

计算字符串中最长有效括号子串的长度，是指在一个由左右括号组成的字符串中，找到最长的连续子串，该子串中的括号是有效配对的。有效配对的括号子串要求每个左括号都能与一个右括号正确匹配，且括号的嵌套顺序正确。这个问题通常通过动态规划或栈的方法来解决，通过遍历字符串并记录有效括号的长度，最终得到最长有效括号子串的长度。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| LongestValidParentheses | class | 计算字符串中最长有效括号子串的长度。 |



## 类 LongestValidParentheses

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | LongestValidParentheses |
| 说明 | 计算字符串中最长有效括号子串的长度。 |


### UML类图

```mermaid
classDiagram
    class LongestValidParentheses {
        +int getLongestValidParentheses(String s)
    }
```

```mermaid
flowchart TD
    A["开始"] --> B{"s == null || s.length() < 2"}
    B -->|是| C["返回0"]
    B -->|否| D["将s转换为字符数组chars"]
    D --> E["初始化数组res"]
    E --> F["设置res[0] = 0"]
    F --> G{"chars[1] == ')' && chars[0] == '('"}
    G -->|是| H["设置res[1] = 2"]
    G -->|否| I["设置res[1] = 0"]
    H --> J["初始化max = res[1]"]
    I --> J
    J --> K["i = 2"]
    K --> L{"i < n"}
    L -->|是| M{"chars[i] == ')'"}
    M -->|是| N{"chars[i - 1] == '('"}
    N -->|是| O["res[i] = res[i - 2] + 2"]
    N -->|否| P["index = i - res[i - 1] - 1"]
    P --> Q{"index >= 0 && chars[index] == '('"}
    Q -->|是| R["res[i] = res[i - 1] + 2 + (index - 1 >= 0 ? res[index - 1] : 0)"]
    Q -->|否| S["res[i] = 0"]
    O --> T["max = Math.max(max, res[i])"]
    R --> T
    S --> T
    T --> U["i++"]
    U --> L
    L -->|否| V["返回max"]
    C --> Z["结束"]
    V --> Z
```

```mermaid
sequenceDiagram
    participant A as 调用者
    participant B as LongestValidParentheses
    A->>B: 调用getLongestValidParentheses("(()))")
    B->>B: 检查s == null || s.length() < 2
    B->>B: 将s转换为字符数组chars
    B->>B: 初始化数组res
    B->>B: 设置res[0] = 0
    B->>B: 设置res[1] = 2
    B->>B: 初始化max = 2
    loop i从2到n-1
        B->>B: 检查chars[i] == ')'
        B->>B: 检查chars[i - 1] == '('
        B->>B: 设置res[i] = res[i - 2] + 2
        B->>B: 更新max = Math.max(max, res[i])
    end
    B->>A: 返回max
```

**描述：**  
`LongestValidParentheses` 类包含一个静态方法 `getLongestValidParentheses`，用于计算给定字符串中最长的有效括号子串的长度。该方法首先检查输入字符串是否为空或长度小于2，如果是则返回0。然后，它将字符串转换为字符数组，并初始化一个数组 `res` 来存储每个位置的最长有效括号长度。通过遍历字符数组，根据当前字符和前一个字符的情况，更新 `res` 数组中的值，并最终返回最大值。流程图展示了该方法的执行逻辑，时序图展示了调用者与 `LongestValidParentheses` 类之间的交互过程。


### 内部方法调用关系图

```mermaid
graph TD
    A["类LongestValidParentheses"]
    B["私有构造方法: LongestValidParentheses()"]
    C["公有静态方法: getLongestValidParentheses(String s)"]
    D["检查输入字符串是否为空或长度小于2"]
    E["返回0"]
    F["将字符串转换为字符数组: s.toCharArray()"]
    G["初始化数组res: int[] res = new int[n]"]
    H["设置res[0] = 0"]
    I["设置res[1] = chars[1] == ')' && chars[0] == '(' ? 2 : 0"]
    J["初始化max为res[1]"]
    K["循环遍历字符数组: for (int i = 2; i < n; ++i)"]
    L["检查当前字符是否为')'"]
    M["检查前一个字符是否为'('"]
    N["更新res[i] = res[i - 2] + 2"]
    O["计算index = i - res[i - 1] - 1"]
    P["检查index是否大于等于0且chars[index] == '('"]
    Q["更新res[i] = res[i - 1] + 2 + (index - 1 >= 0 ? res[index - 1] : 0)"]
    R["更新max为Math.max(max, res[i])"]
    S["返回max"]

    A --> B
    A --> C
    C --> D
    D -->|是| E
    D -->|否| F
    F --> G
    G --> H
    H --> I
    I --> J
    J --> K
    K --> L
    L -->|是| M
    M -->|是| N
    M -->|否| O
    O --> P
    P -->|是| Q
    Q --> R
    L -->|否| R
    R --> K
    K -->|循环结束| S
```

这段代码实现了一个名为`LongestValidParentheses`的类，其中包含一个静态方法`getLongestValidParentheses`，用于计算给定字符串中最长有效括号子串的长度。方法首先检查输入字符串的有效性，然后通过动态规划的方式遍历字符数组，更新每个位置的有效括号长度，并最终返回最大值。流程图展示了该方法的详细执行步骤，包括输入检查、数组初始化、循环遍历、条件判断和结果更新等过程。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getLongestValidParentheses | int | 获取字符串中最长有效括号子串的长度。 |




