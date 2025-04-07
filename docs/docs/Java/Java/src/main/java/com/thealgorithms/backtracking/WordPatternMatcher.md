# 基础信息

|      |      |
|------|------|
| 名称 | WordPatternMatcher |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/backtracking/WordPatternMatcher.java |
| 包名 | com.thealgorithms.backtracking |
| 依赖项 | ['java.util.HashMap', 'java.util.Map'] |
| 概述说明 | WordPatternMatcher类用回溯算法和双向映射表匹配字符串与模式。 |

# 说明

WordPatternMatcher类采用回溯算法来实现字符串与模式的匹配。该算法通过维护两个映射表来确保字符串与模式之间的双向一致性。具体来说，一个映射表用于记录字符串中的字符与模式中的字符之间的对应关系，另一个映射表则用于记录模式中的字符与字符串中的字符之间的对应关系。这种双向映射机制确保了匹配过程的准确性和一致性，使得算法能够有效地判断字符串是否符合给定的模式。通过回溯算法，WordPatternMatcher类能够在遇到不匹配的情况时进行回溯，尝试其他可能的匹配路径，从而提高匹配的成功率。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| WordPatternMatcher | class | WordPatternMatcher类通过回溯算法匹配字符串与模式，使用两个映射表确保双向一致性。 |



## 类 WordPatternMatcher

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | WordPatternMatcher |
| 说明 | WordPatternMatcher类通过回溯算法匹配字符串与模式，使用两个映射表确保双向一致性。 |


### UML类图

```mermaid
classDiagram
    class WordPatternMatcher {
        -WordPatternMatcher()
        +boolean matchWordPattern(String pattern, String inputString)
        -boolean backtrack(String pattern, String inputString, int patternIndex, int strIndex, Map~Character, String~ patternMap, Map~String, Character~ strMap)
    }
```

这段代码定义了一个名为 `WordPatternMatcher` 的类，该类包含一个私有构造函数和一个静态的 `matchWordPattern` 方法，用于判断给定的模式是否与输入字符串匹配。`matchWordPattern` 方法依赖于一个私有的 `backtrack` 方法，该方法通过回溯算法来实现模式匹配。`backtrack` 方法使用两个映射表 `patternMap` 和 `strMap` 来存储模式字符与字符串之间的映射关系，并通过递归调用来检查匹配情况。整个过程通过回溯机制确保所有可能的匹配组合都被尝试，直到找到匹配或确认无匹配为止。


### 内部方法调用关系图

```mermaid
graph TD
    A["类WordPatternMatcher"]
    B["私有构造方法: WordPatternMatcher()"]
    C["静态方法: matchWordPattern(String pattern, String inputString)"]
    D["创建Map: patternMap"]
    E["创建Map: strMap"]
    F["调用方法: backtrack(pattern, inputString, 0, 0, patternMap, strMap)"]
    G["私有静态方法: backtrack(String pattern, String inputString, int patternIndex, int strIndex, Map<Character, String> patternMap, Map<String, Character> strMap)"]
    H["检查条件: patternIndex == pattern.length() && strIndex == inputString.length()"]
    I["返回true"]
    J["检查条件: patternIndex == pattern.length() || strIndex == inputString.length()"]
    K["返回false"]
    L["获取当前字符: currentChar = pattern.charAt(patternIndex)"]
    M["检查条件: patternMap.containsKey(currentChar)"]
    N["获取映射字符串: mappedStr = patternMap.get(currentChar)"]
    O["检查条件: inputString.startsWith(mappedStr, strIndex)"]
    P["递归调用: backtrack(pattern, inputString, patternIndex + 1, strIndex + mappedStr.length(), patternMap, strMap)"]
    Q["返回false"]
    R["循环: for (int end = strIndex + 1; end <= inputString.length(); end++)"]
    S["获取子字符串: substring = inputString.substring(strIndex, end)"]
    T["检查条件: strMap.containsKey(substring)"]
    U["继续循环"]
    V["更新patternMap: patternMap.put(currentChar, substring)"]
    W["更新strMap: strMap.put(substring, currentChar)"]
    X["递归调用: backtrack(pattern, inputString, patternIndex + 1, end, patternMap, strMap)"]
    Y["返回true"]
    Z["移除patternMap: patternMap.remove(currentChar)"]
    AA["移除strMap: strMap.remove(substring)"]
    AB["返回false"]

    A --> B
    A --> C
    C --> D
    C --> E
    C --> F
    F --> G
    G --> H
    H --> I
    G --> J
    J --> K
    G --> L
    L --> M
    M --> N
    N --> O
    O --> P
    O --> Q
    G --> R
    R --> S
    S --> T
    T --> U
    R --> V
    V --> W
    W --> X
    X --> Y
    X --> Z
    Z --> AA
    R --> AB
```

这段代码实现了一个模式匹配器，用于检查给定的模式是否与输入字符串匹配。它使用回溯算法来尝试不同的字符串和模式字符之间的映射关系。代码首先初始化两个映射表，然后通过递归调用回溯函数来尝试匹配。如果找到匹配的映射关系，则返回true，否则返回false。流程图展示了整个匹配过程的逻辑流，包括条件检查和递归调用。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| matchWordPattern | boolean | 匹配字符串模式与输入字符串的双向映射。 |
| backtrack | boolean | 回溯算法匹配字符串与模式。 |




