# 基础信息

|      |      |
|------|------|
| 名称 | FordFulkerson |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/datastructures/graphs/FordFulkerson.java |
| 包名 | com.thealgorithms.datastructures.graphs |
| 依赖项 | ['java.util.LinkedList', 'java.util.Queue'] |
| 概述说明 | Ford-Fulkerson算法用于计算网络中的最大流量。 |

# 说明

Ford-Fulkerson算法是一种用于计算网络最大流的经典方法。该算法通过不断寻找增广路径来增加流量，直到无法找到新的增广路径为止。增广路径是指从源点到汇点的路径，其上的剩余容量大于零。在每次找到增广路径后，算法会更新路径上的流量，并调整剩余容量。最终，当所有可能的增广路径都被遍历后，算法停止并返回网络的最大流值。该算法的关键在于如何高效地寻找增广路径，通常使用深度优先搜索或广度优先搜索来实现。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| FordFulkerson | class | Ford-Fulkerson算法实现，计算网络最大流。 |



## 类 FordFulkerson

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | FordFulkerson |
| 说明 | Ford-Fulkerson算法实现，计算网络最大流。 |


### UML类图

```mermaid
classDiagram
    class FordFulkerson {
        -static final int INF
        +FordFulkerson()
        +static int networkFlow(int vertexCount, int[][] capacity, int[][] flow, int source, int sink)
    }

    class Queue~T~ {
        <<Interface>>
        +boolean add(T e)
        +T poll()
        +boolean isEmpty()
    }

    class LinkedList~T~ {
        +boolean add(T e)
        +T poll()
        +boolean isEmpty()
    }

    FordFulkerson --> Queue~Integer~ : 使用
    Queue~Integer~ <|.. LinkedList~Integer~ : 实现
```

这段代码实现了Ford-Fulkerson算法，用于计算流网络中的最大流。`FordFulkerson`类包含一个静态方法`networkFlow`，该方法通过广度优先搜索（BFS）寻找增广路径，并更新流值，直到无法找到新的增广路径为止。代码中使用了`Queue`接口和其实现类`LinkedList`来管理待处理的顶点。通过不断调整流值，最终计算出从源点到汇点的最大流。


### 内部方法调用关系图

```mermaid
graph TD
    A["类FordFulkerson"]
    B["常量: int INF = Integer.MAX_VALUE"]
    C["私有构造方法: FordFulkerson()"]
    D["方法: networkFlow(int vertexCount, int[][] capacity, int[][] flow, int source, int sink)"]
    E["初始化: int totalFlow = 0"]
    F["循环: while (true)"]
    G["初始化: int[] parent = new int[vertexCount]"]
    H["初始化: boolean[] visited = new boolean[vertexCount]"]
    I["初始化: Queue<Integer> queue = new LinkedList<>()"]
    J["添加源节点: queue.add(source)"]
    K["标记源节点: visited[source] = true"]
    L["设置父节点: parent[source] = -1"]
    M["循环: while (!queue.isEmpty() && !visited[sink])"]
    N["获取当前节点: int current = queue.poll()"]
    O["遍历邻接节点: for (int next = 0; next < vertexCount; next++)"]
    P["检查条件: if (!visited[next] && capacity[current][next] - flow[current][next] > 0)"]
    Q["添加邻接节点: queue.add(next)"]
    R["标记邻接节点: visited[next] = true"]
    S["设置父节点: parent[next] = current"]
    T["检查终止条件: if (!visited[sink])"]
    U["退出循环: break"]
    V["初始化路径流量: int pathFlow = INF"]
    W["计算路径流量: for (int v = sink; v != source; v = parent[v])"]
    X["更新路径流量: pathFlow = Math.min(pathFlow, capacity[u][v] - flow[u][v])"]
    Y["更新流量: for (int v = sink; v != source; v = parent[v])"]
    Z["增加正向流量: flow[u][v] += pathFlow"]
    AA["减少反向流量: flow[v][u] -= pathFlow"]
    AB["累加总流量: totalFlow += pathFlow"]
    AC["返回总流量: return totalFlow"]

    A --> B
    A --> C
    A --> D
    D --> E
    D --> F
    F --> G
    F --> H
    F --> I
    F --> J
    J --> K
    K --> L
    F --> M
    M --> N
    M --> O
    O --> P
    P --> Q
    Q --> R
    R --> S
    F --> T
    T --> U
    F --> V
    V --> W
    W --> X
    F --> Y
    Y --> Z
    Z --> AA
    F --> AB
    D --> AC
```

这段代码实现了Ford-Fulkerson算法，用于计算流网络中的最大流量。算法通过不断寻找增广路径来增加流量，直到无法找到新的增广路径为止。代码初始化了父节点数组和访问标记数组，使用广度优先搜索（BFS）来寻找增广路径，并更新流量矩阵。最终返回从源节点到汇节点的最大流量。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| INF = Integer.MAX_VALUE | int | 定义私有静态常量INF为整型最大值。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| networkFlow | int | 网络流算法计算源点到汇点的最大流量。 |




