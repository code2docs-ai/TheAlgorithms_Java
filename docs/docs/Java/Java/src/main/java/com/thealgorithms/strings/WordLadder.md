# 基础信息

|      |      |
|------|------|
| 名称 | WordLadder |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/strings/WordLadder.java |
| 包名 | com.thealgorithms.strings |
| 依赖项 | ['java.util.Collection', 'java.util.HashSet', 'java.util.LinkedList', 'java.util.Queue', 'java.util.Set'] |
| 概述说明 | WordLadder类用于查找最短词转换序列，无序列时返回0。 |

# 说明

WordLadder类的主要功能是查找从给定的起始词到目标词的最短转换序列。它通过一系列步骤将起始词逐步转换为目标词，每次转换只改变一个字母，且每次转换后的词必须存在于词典中。如果存在这样的转换序列，WordLadder类将返回该序列的长度；如果无法找到任何有效的转换序列，则返回0。该类的核心目标是高效地确定最短转换路径，确保结果的准确性和最优性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| WordLadder | class | WordLadder类用于查找从起始词到目标词的最短转换序列，返回序列长度或无序列时返回0。 |



## 类 WordLadder

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | WordLadder |
| 说明 | WordLadder类用于查找从起始词到目标词的最短转换序列，返回序列长度或无序列时返回0。 |


### UML类图

```mermaid
classDiagram
    class WordLadder {
        -WordLadder()
        +int ladderLength(String beginWord, String endWord, Collection~String~ wordList)
    }
```

**描述：**  
`WordLadder` 类是一个工具类，用于计算从 `beginWord` 到 `endWord` 的最短转换序列的长度。该类包含一个私有构造函数，确保无法实例化。`ladderLength` 方法接受起始词、目标词和词列表作为参数，通过广度优先搜索（BFS）算法找到最短转换序列的长度。如果无法找到转换序列，则返回 0。该方法通过逐字符替换和队列操作来探索所有可能的转换路径。


### 内部方法调用关系图

```mermaid
graph TD
    A["类WordLadder"]
    B["构造方法: WordLadder()"]
    C["静态方法: ladderLength(String beginWord, String endWord, Collection<String> wordList)"]
    D["创建Set<String> wordSet = new HashSet<>(wordList)"]
    E["检查wordSet是否包含endWord"]
    F["返回0"]
    G["创建Queue<String> queue = new LinkedList<>()"]
    H["queue.offer(beginWord)"]
    I["初始化int level = 1"]
    J["检查queue是否为空"]
    K["获取queue的大小int size = queue.size()"]
    L["循环i从0到size"]
    M["String currentWord = queue.poll()"]
    N["char[] currentWordChars = currentWord.toCharArray()"]
    O["循环j从0到currentWordChars.length"]
    P["保存originalChar = currentWordChars[j]"]
    Q["循环c从'a'到'z'"]
    R["检查currentWordChars[j] == c"]
    S["跳过当前循环"]
    T["currentWordChars[j] = c"]
    U["创建String newWord = new String(currentWordChars)"]
    V["检查newWord.equals(endWord)"]
    W["返回level + 1"]
    X["检查wordSet.remove(newWord)"]
    Y["queue.offer(newWord)"]
    Z["恢复currentWordChars[j] = originalChar"]
    AA["level++"]
    AB["返回0"]

    A --> B
    A --> C
    C --> D
    D --> E
    E --"否"--> F
    E --"是"--> G
    G --> H
    H --> I
    I --> J
    J --"是"--> K
    K --> L
    L --> M
    M --> N
    N --> O
    O --> P
    P --> Q
    Q --> R
    R --"是"--> S
    R --"否"--> T
    T --> U
    U --> V
    V --"是"--> W
    V --"否"--> X
    X --"是"--> Y
    Y --> Z
    Z --> Q
    Q --"循环结束"--> O
    O --"循环结束"--> L
    L --"循环结束"--> AA
    AA --> J
    J --"否"--> AB
```

这段代码实现了一个单词梯子算法，用于找到从起始单词到目标单词的最短转换序列。代码通过广度优先搜索（BFS）遍历所有可能的单词变换，并在找到目标单词时返回转换序列的长度。流程图展示了从初始化到最终返回结果的完整流程，包括单词集合的创建、队列的使用、字符变换的循环以及条件判断等关键步骤。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| ladderLength | int | 该方法计算从起始词到目标词的最短转换路径长度，使用广度优先搜索和字符替换策略。 |




