# 基础信息

|      |      |
|------|------|
| 名称 | MinStackUsingSingleStack |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/stacks/MinStackUsingSingleStack.java |
| 包名 | com.thealgorithms.stacks |
| 依赖项 | ['java.util.EmptyStackException', 'java.util.Stack'] |
| 概述说明 | 单栈实现最小栈，存储值与当前最小，支持入栈、出栈、获取栈顶和最小值操作。 |

# 说明

单栈实现最小栈的方法是通过在栈中同时存储元素值和当前最小值。该结构支持入栈操作，将新元素及其对应的最小值压入栈中；出栈操作，移除栈顶元素；获取栈顶元素，返回栈顶的值；以及获取最小值操作，返回栈顶记录的最小值。这种方法确保了在常数时间内能够获取栈中的最小值，同时保持了栈的基本功能。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| MinStackUsingSingleStack | class | 单栈实现最小栈，存储值和当前最小值，支持入栈、出栈、获取栈顶和最小值操作。 |



## 类 MinStackUsingSingleStack

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | MinStackUsingSingleStack |
| 说明 | 单栈实现最小栈，存储值和当前最小值，支持入栈、出栈、获取栈顶和最小值操作。 |


### UML类图

```mermaid
classDiagram
    class MinStackUsingSingleStack {
        -Stack~long[]~ stack
        +void push(int value)
        +void pop()
        +int top()
        +int getMin()
    }
```

类图描述：`MinStackUsingSingleStack` 类实现了一个支持获取最小值的栈结构。它使用一个 `Stack<long[]>` 来存储元素，其中每个元素是一个包含当前值和当前最小值的数组。类提供了 `push`、`pop`、`top` 和 `getMin` 方法，分别用于压入元素、弹出栈顶元素、获取栈顶元素以及获取当前栈中的最小值。通过这种方式，可以在常数时间内获取栈中的最小值。


### 内部方法调用关系图

```mermaid
graph TD
    A["类MinStackUsingSingleStack"]
    B["属性: Stack<long[]> stack"]
    C["方法: void push(int value)"]
    D["条件: stack.isEmpty()"]
    E["操作: stack.push(new long[] {value, value})"]
    F["操作: long minSoFar = Math.min(value, stack.peek()[1])"]
    G["操作: stack.push(new long[] {value, minSoFar})"]
    H["方法: void pop()"]
    I["条件: !stack.isEmpty()"]
    J["操作: stack.pop()"]
    K["方法: int top()"]
    L["条件: !stack.isEmpty()"]
    M["操作: return (int) stack.peek()[0]"]
    N["异常: throw new EmptyStackException()"]
    O["方法: int getMin()"]
    P["条件: !stack.isEmpty()"]
    Q["操作: return (int) stack.peek()[1]"]
    R["异常: throw new EmptyStackException()"]

    A --> B
    A --> C
    C --> D
    D -->|是| E
    D -->|否| F
    F --> G
    A --> H
    H --> I
    I -->|是| J
    A --> K
    K --> L
    L -->|是| M
    L -->|否| N
    A --> O
    O --> P
    P -->|是| Q
    P -->|否| R
```

这段代码实现了一个最小栈（MinStack），使用单个栈来存储元素及其当前最小值。`push`方法将新元素和当前最小值一起压入栈中；`pop`方法移除栈顶元素；`top`方法返回栈顶元素；`getMin`方法返回栈中的最小值。通过这种方式，可以在常数时间内获取最小值，同时保持栈的基本操作效率。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| stack = new Stack<>() | Stack<long[]> | 声明一个存储长整型数组的私有栈对象。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| push | void | 方法`push`将值及其当前最小值压入栈中。 |
| pop | void | 该方法检查栈非空后执行弹出操作。 |
| getMin | int | 获取栈中最小元素，若栈空则抛出异常。 |
| top | int | 获取栈顶元素，若栈为空则抛出异常。 |




