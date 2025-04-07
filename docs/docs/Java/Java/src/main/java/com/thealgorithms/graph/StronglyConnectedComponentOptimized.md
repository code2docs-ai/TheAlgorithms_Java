# 基础信息

|      |      |
|------|------|
| 名称 | StronglyConnectedComponentOptimized |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/graph/StronglyConnectedComponentOptimized.java |
| 包名 | com.thealgorithms.graph |
| 依赖项 | ['java.util.ArrayList', 'java.util.Arrays', 'java.util.HashMap', 'java.util.List', 'java.util.Stack'] |
| 概述说明 | 优化强连通分量算法，利用回溯和反向图计算数量。 |

# 说明

优化强连通分量算法的方法包括使用回溯技术和反向图计算。回溯技术通过递归探索图中的节点，确保每个节点都被正确标记为强连通分量的一部分。反向图计算则通过构建原图的反向图，利用深度优先搜索（DFS）来确定强连通分量的数量。这种方法能够有效减少计算复杂度，提高算法效率，确保在复杂图中快速准确地识别所有强连通分量。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| StronglyConnectedComponentOptimized | class | 优化强连通分量算法，通过回溯和反向图计算强连通分量数量。 |



## 类 StronglyConnectedComponentOptimized

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | StronglyConnectedComponentOptimized |
| 说明 | 优化强连通分量算法，通过回溯和反向图计算强连通分量数量。 |


### UML类图

```mermaid
classDiagram
    class StronglyConnectedComponentOptimized {
        +btrack(HashMap~Integer, List~Integer~~ adjList, int[] visited, Stack~Integer~ dfsCallsNodes, int currentNode) void
        +btrack2(HashMap~Integer, List~Integer~~ adjRevList, int[] visited, int currentNode, List~Integer~ newScc) void
        +getOutput(HashMap~Integer, List~Integer~~ adjList, int n) int
    }
```

```mermaid
flowchart TD
    A["开始"] --> B["初始化visited数组和dfsCallsNodes栈"]
    B --> C["遍历所有节点"]
    C --> D{"visited[i] == -1?"}
    D -- 是 --> E["调用btrack方法"]
    D -- 否 --> C
    E --> F["构建反向邻接表adjRevList"]
    F --> G["重置visited数组"]
    G --> H["遍历dfsCallsNodes栈"]
    H --> I{"visited[node] == -1?"}
    I -- 是 --> J["调用btrack2方法"]
    I -- 否 --> H
    J --> K["增加强连通分量计数"]
    K --> H
    H --> L["返回强连通分量数量"]
    L --> M["结束"]
```

```mermaid
sequenceDiagram
    participant Main
    participant StronglyConnectedComponentOptimized
    Main->>StronglyConnectedComponentOptimized: getOutput(adjList, n)
    StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: 初始化visited数组和dfsCallsNodes栈
    loop 遍历所有节点
        StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: visited[i] == -1?
        alt 是
            StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: 调用btrack方法
        end
    end
    StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: 构建反向邻接表adjRevList
    StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: 重置visited数组
    loop 遍历dfsCallsNodes栈
        StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: visited[node] == -1?
        alt 是
            StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: 调用btrack2方法
            StronglyConnectedComponentOptimized->>StronglyConnectedComponentOptimized: 增加强连通分量计数
        end
    end
    StronglyConnectedComponentOptimized->>Main: 返回强连通分量数量
```

**描述：**
`StronglyConnectedComponentOptimized` 类用于计算有向图中的强连通分量数量。通过深度优先搜索（DFS）遍历图，构建反向邻接表，并再次使用DFS遍历反向图，最终统计强连通分量的数量。该类包含三个主要方法：`btrack` 用于首次DFS遍历，`btrack2` 用于反向图的DFS遍历，`getOutput` 负责初始化、调用上述方法并返回结果。


### 内部方法调用关系图

```mermaid
graph TD
    A["类StronglyConnectedComponentOptimized"]
    B["方法: btrack(HashMap<Integer, List<Integer>> adjList, int[] visited, Stack<Integer> dfsCallsNodes, int currentNode)"]
    C["方法: btrack2(HashMap<Integer, List<Integer>> adjRevList, int[] visited, int currentNode, List<Integer> newScc)"]
    D["方法: getOutput(HashMap<Integer, List<Integer>> adjList, int n)"]
    E["初始化: int[] visited = new int[n]"]
    F["填充: Arrays.fill(visited, -1)"]
    G["初始化: Stack<Integer> dfsCallsNodes = new Stack<>()"]
    H["遍历: for (int i = 0; i < n; i++)"]
    I["条件: if (visited[i] == -1)"]
    J["调用: btrack(adjList, visited, dfsCallsNodes, i)"]
    K["初始化: HashMap<Integer, List<Integer>> adjRevList = new HashMap<>()"]
    L["遍历: for (int i = 0; i < n; i++)"]
    M["初始化: adjRevList.put(i, new ArrayList<>())"]
    N["遍历: for (int i = 0; i < n; i++)"]
    O["获取: List<Integer> neighbors = adjList.get(i)"]
    P["条件: if (neighbors != null)"]
    Q["遍历: for (int neighbor : neighbors)"]
    R["添加: adjRevList.get(neighbor).add(i)"]
    S["填充: Arrays.fill(visited, -1)"]
    T["初始化: int stronglyConnectedComponents = 0"]
    U["循环: while (!dfsCallsNodes.isEmpty())"]
    V["弹出: int node = dfsCallsNodes.pop()"]
    W["条件: if (visited[node] == -1)"]
    X["初始化: List<Integer> newScc = new ArrayList<>()"]
    Y["调用: btrack2(adjRevList, visited, node, newScc)"]
    Z["增加: stronglyConnectedComponents++"]
    AA["返回: return stronglyConnectedComponents"]

    A --> B
    A --> C
    A --> D
    D --> E
    D --> F
    D --> G
    D --> H
    H --> I
    I --> J
    D --> K
    D --> L
    L --> M
    D --> N
    N --> O
    O --> P
    P --> Q
    Q --> R
    D --> S
    D --> T
    D --> U
    U --> V
    V --> W
    W --> X
    W --> Y
    Y --> Z
    D --> AA
```

这段代码实现了一个优化后的强连通分量（SCC）算法。它首先通过深度优先搜索（DFS）遍历图，将节点按访问顺序压入栈中。然后，通过反转图的邻接表，再次使用DFS遍历栈中的节点，找到所有的强连通分量。最终，返回强连通分量的数量。代码中使用了两个递归方法 `btrack` 和 `btrack2` 分别进行DFS遍历和反转图的DFS遍历。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getOutput | int | 通过深度优先搜索计算有向图的强连通分量数量。 |
| btrack2 | void | 递归遍历邻接表，标记已访问节点并收集强连通分量。 |
| btrack | void | 递归遍历邻接表，标记访问节点并记录DFS调用顺序。 |




