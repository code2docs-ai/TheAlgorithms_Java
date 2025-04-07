# 基础信息

|      |      |
|------|------|
| 名称 | StackUsingTwoQueues |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/stacks/StackUsingTwoQueues.java |
| 包名 | com.thealgorithms.stacks |
| 依赖项 | ['java.util.LinkedList', 'java.util.NoSuchElementException', 'java.util.Queue'] |
| 概述说明 | 双队列实现栈，支持压栈、弹栈、查看栈顶、判空及获取大小功能。 |

# 说明

使用两个队列实现栈结构，该结构支持多种操作，包括压栈、弹栈、查看栈顶元素、判断栈是否为空以及获取栈的大小。通过巧妙地利用两个队列的先进先出特性，可以实现栈的后进先出特性。具体实现过程中，两个队列交替作为主队列和辅助队列，确保栈操作的正确性和高效性。这种方法在保证功能完整性的同时，也展示了数据结构之间的灵活转换和高效利用。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| StackUsingTwoQueues | class | 使用两个队列实现栈，支持压栈、弹栈、查看栈顶、判空和获取大小操作。 |



## 类 StackUsingTwoQueues

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | StackUsingTwoQueues |
| 说明 | 使用两个队列实现栈，支持压栈、弹栈、查看栈顶、判空和获取大小操作。 |


### UML类图

```mermaid
classDiagram
    class StackUsingTwoQueues {
        -Queue~Integer~ mainQueue
        -Queue~Integer~ tempQueue
        +StackUsingTwoQueues()
        +void push(int item)
        +int pop()
        +Integer peek()
        +boolean isEmpty()
        +int size()
    }
```

```mermaid
flowchart TD
    A["push(item)"] --> B["tempQueue.add(item)"]
    B --> C{"mainQueue.isEmpty()?"}
    C -- Yes --> D["Swap mainQueue and tempQueue"]
    C -- No --> E["tempQueue.add(mainQueue.remove())"]
    E --> C
    D --> F["End"]

    G["pop()"] --> H{"mainQueue.isEmpty()?"}
    H -- Yes --> I["Throw NoSuchElementException"]
    H -- No --> J["Return mainQueue.remove()"]

    K["peek()"] --> L{"mainQueue.isEmpty()?"}
    L -- Yes --> M["Return null"]
    L -- No --> N["Return mainQueue.peek()"]

    O["isEmpty()"] --> P["Return mainQueue.isEmpty()"]

    Q["size()"] --> R["Return mainQueue.size()"]
```

```mermaid
sequenceDiagram
    participant User
    participant StackUsingTwoQueues
    User->>StackUsingTwoQueues: push(item)
    StackUsingTwoQueues->>StackUsingTwoQueues: tempQueue.add(item)
    loop until mainQueue is empty
        StackUsingTwoQueues->>StackUsingTwoQueues: tempQueue.add(mainQueue.remove())
    end
    StackUsingTwoQueues->>StackUsingTwoQueues: Swap mainQueue and tempQueue
    StackUsingTwoQueues-->>User: End

    User->>StackUsingTwoQueues: pop()
    alt mainQueue is empty
        StackUsingTwoQueues-->>User: Throw NoSuchElementException
    else
        StackUsingTwoQueues-->>User: Return mainQueue.remove()
    end

    User->>StackUsingTwoQueues: peek()
    alt mainQueue is empty
        StackUsingTwoQueues-->>User: Return null
    else
        StackUsingTwoQueues-->>User: Return mainQueue.peek()
    end

    User->>StackUsingTwoQueues: isEmpty()
    StackUsingTwoQueues-->>User: Return mainQueue.isEmpty()

    User->>StackUsingTwoQueues: size()
    StackUsingTwoQueues-->>User: Return mainQueue.size()
```

**描述**：  
`StackUsingTwoQueues` 类使用两个队列实现了栈的数据结构。`push` 方法将元素压入栈顶，通过将元素先加入临时队列，再将主队列中的所有元素转移到临时队列，最后交换两个队列的引用，确保新元素位于栈顶。`pop` 方法移除并返回栈顶元素，若栈为空则抛出异常。`peek` 方法返回栈顶元素但不移除，若栈为空则返回 `null`。`isEmpty` 和 `size` 方法分别用于判断栈是否为空和获取栈的大小。


### 内部方法调用关系图

```mermaid
graph TD
    A["类StackUsingTwoQueues"]
    B["属性: Queue<Integer> mainQueue"]
    C["属性: Queue<Integer> tempQueue"]
    D["构造方法: StackUsingTwoQueues()"]
    E["方法: void push(int item)"]
    F["方法: int pop()"]
    G["方法: Integer peek()"]
    H["方法: boolean isEmpty()"]
    I["方法: int size()"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    A --> I

    E --> E1["tempQueue.add(item)"]
    E --> E2["while (!mainQueue.isEmpty())"]
    E2 --> E3["tempQueue.add(mainQueue.remove())"]
    E --> E4["交换mainQueue和tempQueue"]

    F --> F1["if (mainQueue.isEmpty())"]
    F1 --> F2["抛出NoSuchElementException"]
    F --> F3["返回mainQueue.remove()"]

    G --> G1["if (mainQueue.isEmpty())"]
    G1 --> G2["返回null"]
    G --> G3["返回mainQueue.peek()"]

    H --> H1["返回mainQueue.isEmpty()"]

    I --> I1["返回mainQueue.size()"]
```

这段代码实现了一个使用两个队列模拟栈的类。栈的LIFO（后进先出）特性通过维护两个队列来实现，`push`操作通过将元素添加到临时队列并交换主队列和临时队列的顺序来保持栈的顺序。`pop`、`peek`、`isEmpty`和`size`方法分别用于移除栈顶元素、查看栈顶元素、检查栈是否为空以及获取栈的大小。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| tempQueue | Queue<Integer> | 私有队列存储整数类型数据。 |
| mainQueue | Queue<Integer> | 私有整型队列mainQueue。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| isEmpty | boolean | 检查主队列是否为空。 |
| push | void | 使用两个队列实现栈的push操作，确保LIFO顺序。 |
| pop | int | 弹出栈顶元素，若栈为空则抛出异常。 |
| size | int | 该方法返回主队列的大小。 |
| peek | Integer | peek方法检查主队列是否为空，若空返回null，否则返回队列头部元素。 |




