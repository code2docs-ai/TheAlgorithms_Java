# 基础信息

|      |      |
|------|------|
| 名称 | HamiltonianCycle |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/datastructures/graphs/HamiltonianCycle.java |
| 包名 | com.thealgorithms.datastructures.graphs |
| 依赖项 | ['java.util.Arrays'] |
| 概述说明 | HamiltonianCycle类递归搜索邻接矩阵寻找哈密顿环，找到返回顶点序列，否则返回-1。 |

# 说明

HamiltonianCycle类采用递归方法遍历图的邻接矩阵，以寻找是否存在哈密顿环。如果成功找到哈密顿环，该类将返回环中顶点的序列；如果未找到，则返回-1。该过程通过系统地检查图中的所有可能路径，确保能够确定是否存在一个经过每个顶点一次且仅一次的闭合环。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| HamiltonianCycle | class | HamiltonianCycle类通过递归搜索图的邻接矩阵，寻找哈密顿环。若找到，返回环的顶点序列；否则返回-1。 |



## 类 HamiltonianCycle

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | HamiltonianCycle |
| 说明 | HamiltonianCycle类通过递归搜索图的邻接矩阵，寻找哈密顿环。若找到，返回环的顶点序列；否则返回-1。 |


### UML类图

```mermaid
classDiagram
    class HamiltonianCycle {
        -int vertex
        -int pathCount
        -int[] cycle
        -int[][] graph
        +int[] findHamiltonianCycle(int[][] graph)
        +boolean isPathFound(int vertex)
        +boolean isPresent(int vertex)
    }
```

**描述：**  
`HamiltonianCycle` 类用于在给定的图中寻找哈密顿回路。该类通过递归方法 `isPathFound` 来探索可能的路径，并使用 `isPresent` 方法检查顶点是否已存在于当前路径中。`findHamiltonianCycle` 方法初始化并返回找到的哈密顿回路，若未找到则返回包含 `-1` 的数组。该类通过邻接矩阵表示图结构，并通过回溯算法实现路径搜索。


### 内部方法调用关系图

```mermaid
graph TD
    A["类HamiltonianCycle"]
    B["属性: int vertex"]
    C["属性: int pathCount"]
    D["属性: int[] cycle"]
    E["属性: int[][] graph"]
    F["方法: int[] findHamiltonianCycle(int[][] graph)"]
    G["方法: boolean isPathFound(int vertex)"]
    H["方法: boolean isPresent(int vertex)"]
    I["判断: graph.length == 1"]
    J["初始化: this.vertex = graph.length"]
    K["初始化: this.cycle = new int[this.vertex + 1]"]
    L["初始化: Arrays.fill(this.cycle, -1)"]
    M["设置: this.cycle[0] = 0"]
    N["设置: this.pathCount = 1"]
    O["调用: isPathFound(0)"]
    P["判断: isPathFound(0) == false"]
    Q["填充: Arrays.fill(this.cycle, -1)"]
    R["设置: this.cycle[this.cycle.length - 1] = this.cycle[0]"]
    S["返回: cycle"]
    T["判断: this.graph[vertex][0] == 1 && this.pathCount == this.vertex"]
    U["返回: true"]
    V["判断: this.pathCount == this.vertex"]
    W["返回: false"]
    X["循环: for (int v = 0; v < this.vertex; v++)"]
    Y["判断: this.graph[vertex][v] == 1"]
    Z["设置: this.cycle[this.pathCount++] = v"]
    AA["设置: this.graph[vertex][v] = 0"]
    AB["设置: this.graph[v][vertex] = 0"]
    AC["调用: isPresent(v)"]
    AD["调用: isPathFound(v)"]
    AE["恢复: this.graph[vertex][v] = 1"]
    AF["恢复: this.graph[v][vertex] = 1"]
    AG["设置: this.cycle[--this.pathCount] = -1"]
    AH["返回: false"]
    AI["循环: for (int i = 0; i < pathCount - 1; i++)"]
    AJ["判断: cycle[i] == vertex"]
    AK["返回: true"]
    AL["返回: false"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    F --> I
    I -->|是| S
    I -->|否| J
    J --> K
    K --> L
    L --> M
    M --> N
    N --> O
    O --> P
    P -->|是| Q
    Q --> S
    P -->|否| R
    R --> S
    G --> T
    T -->|是| U
    T -->|否| V
    V -->|是| W
    V -->|否| X
    X --> Y
    Y -->|是| Z
    Z --> AA
    AA --> AB
    AB --> AC
    AC -->|否| AD
    AD -->|是| U
    AD -->|否| AE
    AE --> AF
    AF --> AG
    AG --> AH
    Y -->|否| AH
    H --> AI
    AI --> AJ
    AJ -->|是| AK
    AJ -->|否| AL
```

**描述**：这段代码实现了哈密顿环的查找算法。首先，`findHamiltonianCycle`方法初始化图的相关属性，并调用`isPathFound`方法递归地查找哈密顿环。`isPathFound`方法通过深度优先搜索遍历图中的顶点，尝试构建一个哈密顿环。`isPresent`方法用于检查某个顶点是否已经在当前路径中。如果找到哈密顿环，返回环的顶点序列；否则返回一个填充为-1的数组表示未找到。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| vertex | int | 定义了一个私有整型变量vertex。 |
| graph | int[][] | 定义了一个私有的二维整型数组graph。 |
| pathCount | int | 私有整型变量pathCount用于计数路径数量。 |
| cycle | int[] | 定义了一个私有的整型数组cycle。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| isPresent | boolean | 检查顶点是否存在于循环路径中。 |
| isPathFound | boolean | 方法检查图中是否存在从指定顶点到起点的闭合路径。 |
| findHamiltonianCycle | int[] | 查找哈密顿环的算法实现，初始化并回溯求解。 |




