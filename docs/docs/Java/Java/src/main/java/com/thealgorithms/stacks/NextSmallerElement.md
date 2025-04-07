# 基础信息

|      |      |
|------|------|
| 名称 | NextSmallerElement |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/stacks/NextSmallerElement.java |
| 包名 | com.thealgorithms.stacks |
| 依赖项 | ['java.util.Arrays', 'java.util.Stack'] |
| 概述说明 | 查找数组中每个元素左侧下一个更小的元素，若无则返回-1。 |

# 说明

该问题要求查找数组中每个元素左侧的下一个更小的元素。具体来说，对于数组中的每一个元素，需要在其左侧寻找第一个比它小的元素，并返回该元素的值。如果左侧没有比当前元素更小的元素，则返回-1。这个问题通常用于处理单调栈相关的算法场景，能够有效解决类似查找最近较小值的问题。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| NextSmallerElement | class | 查找数组中每个元素左侧下一个更小的元素，若无则返回-1。 |



## 类 NextSmallerElement

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | NextSmallerElement |
| 说明 | 查找数组中每个元素左侧下一个更小的元素，若无则返回-1。 |


### UML类图

```mermaid
classDiagram
    class NextSmallerElement {
        +findNextSmallerElements(int[] array) int[]
        -NextSmallerElement()
    }
    class Stack~Integer~ {
        +push(Integer element) void
        +pop() Integer
        +peek() Integer
        +isEmpty() boolean
    }
    class Arrays {
        +fill(int[] a, int val) void
    }
    NextSmallerElement --> Arrays : 依赖
    NextSmallerElement --> Stack~Integer~ : 依赖
```

### 描述
`NextSmallerElement` 类包含一个静态方法 `findNextSmallerElements`，用于查找数组中每个元素的下一个较小元素。该方法使用 `Stack` 数据结构来维护当前元素的较小元素，并通过 `Arrays` 类初始化结果数组。`Stack` 类提供了基本的栈操作，如 `push`、`pop`、`peek` 和 `isEmpty`。`Arrays` 类提供了 `fill` 方法，用于将数组的所有元素初始化为指定值。


### 内部方法调用关系图

```mermaid
graph TD
    A["类NextSmallerElement"]
    B["私有构造方法: NextSmallerElement()"]
    C["静态方法: int[] findNextSmallerElements(int[] array)"]
    D["检查输入数组是否为null"]
    E["抛出异常: IllegalArgumentException"]
    F["初始化结果数组result"]
    G["初始化栈stack"]
    H["填充result数组为-1"]
    I["遍历数组元素"]
    J["维护栈结构"]
    K["弹出栈顶元素"]
    L["检查栈是否为空"]
    M["将栈顶元素赋给result[i]"]
    N["将当前元素压入栈"]
    O["返回结果数组result"]

    A --> B
    A --> C
    C --> D
    D -->|是| E
    D -->|否| F
    F --> G
    G --> H
    H --> I
    I --> J
    J -->|栈不为空且栈顶元素>=当前元素| K
    K --> J
    J -->|栈不为空| L
    L --> M
    M --> N
    N --> I
    I -->|遍历结束| O
```

这段代码定义了一个名为`NextSmallerElement`的类，其中包含一个静态方法`findNextSmallerElements`，用于查找数组中每个元素的左侧下一个较小元素。方法首先检查输入数组是否为null，若为null则抛出异常。接着初始化结果数组和栈，遍历数组时维护栈结构以确保栈顶元素始终是当前元素的下一个较小元素，最终返回结果数组。流程图展示了方法的执行流程和逻辑判断。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| findNextSmallerElements | int[] | 查找数组中每个元素的下一个较小元素，使用栈实现，结果初始为-1。 |




