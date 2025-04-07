# 基础信息

|      |      |
|------|------|
| 名称 | KahnsAlgorithm |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/datastructures/graphs/KahnsAlgorithm.java |
| 包名 | com.thealgorithms.datastructures.graphs |
| 依赖项 | ['java.util.ArrayList', 'java.util.HashMap', 'java.util.LinkedHashMap', 'java.util.LinkedList', 'java.util.Map', 'java.util.Queue', 'java.util.Set'] |
| 概述说明 | 实现有向图邻接表，支持添加边、获取邻接顶点和所有顶点。提供拓扑排序功能，使用Kahn算法，检测环并返回排序结果。 |

# 说明

AdjacencyList类实现了有向图的邻接表结构，支持添加边、获取邻接顶点和所有顶点功能。TopologicalSort类实现了图的拓扑排序算法，通过计算每个顶点的入度并返回排序后的顶点列表，若图中存在环则抛出异常。Kahn算法同样用于图的拓扑排序，确保输出节点的正确顺序。这些类共同提供了图的表示和拓扑排序的完整解决方案。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| AdjacencyList | class | AdjacencyList类实现有向图邻接表，支持添加边、获取邻接顶点和所有顶点。 |
| TopologicalSort | class | TopologicalSort类实现图的拓扑排序，计算入度并返回排序后的顶点列表，若图有环则抛出异常。 |
| KahnsAlgorithm | class | Kahn算法实现图的拓扑排序，输出节点顺序。 |



## 类 AdjacencyList

|      |      |
|------|------|
| 访问范围 | None |
| 类型 | class |
| 名称 | AdjacencyList |
| 说明 | AdjacencyList类实现有向图邻接表，支持添加边、获取邻接顶点和所有顶点。 |


### UML类图

```mermaid
classDiagram
    class AdjacencyList~E extends Comparable~E~~ {
        -Map~E, ArrayList~E~~ adj
        +AdjacencyList()
        +void addEdge(E from, E to)
        +ArrayList~E~ getAdjacents(E v)
        +Set~E~ getVertices()
    }
```

### 描述
`AdjacencyList` 类用于表示图的邻接表结构，其中泛型 `E` 必须实现 `Comparable` 接口。该类包含一个 `Map` 类型的私有成员 `adj`，用于存储顶点及其相邻顶点的列表。类提供了构造方法 `AdjacencyList()` 来初始化邻接表，以及 `addEdge(E from, E to)` 方法来添加有向边，`getAdjacents(E v)` 方法用于获取指定顶点的相邻顶点列表，`getVertices()` 方法用于获取图中所有顶点的集合。


### 内部方法调用关系图

```mermaid
graph TD
    A["类AdjacencyList<E extends Comparable<E>>"]
    B["属性: Map<E, ArrayList<E>> adj"]
    C["构造方法: AdjacencyList()"]
    D["方法: void addEdge(E from, E to)"]
    E["方法: ArrayList<E> getAdjacents(E v)"]
    F["方法: Set<E> getVertices()"]
    G["检查: adj.containsKey(from)"]
    H["操作: adj.put(from, new ArrayList<>())"]
    I["操作: adj.get(from).add(to)"]
    J["检查: adj.containsKey(to)"]
    K["操作: adj.put(to, new ArrayList<>())"]
    L["返回: adj.get(v)"]
    M["返回: adj.keySet()"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    D --> G
    G -->|否| H
    H --> I
    I --> J
    J -->|否| K
    G -->|是| I
    J -->|是| I
    E --> L
    F --> M
```

该流程图描述了`AdjacencyList`类的结构及其方法调用关系。`AdjacencyList`类用于表示图的邻接表，包含一个`Map`属性`adj`，用于存储顶点及其相邻顶点列表。类中的方法包括`addEdge`用于添加有向边，`getAdjacents`用于获取某个顶点的相邻顶点列表，`getVertices`用于获取图中所有顶点的集合。流程图详细展示了`addEdge`方法中的逻辑判断和操作步骤。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| adj | Map<E, ArrayList<E>> | 映射结构存储元素与其关联元素列表。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| addEdge | void | 添加有向边，更新邻接表。 |
| getAdjacents | ArrayList<E> | 获取指定元素的相邻元素列表。 |
| getVertices | Set<E> | 获取图中所有顶点的集合。 |



## 类 TopologicalSort

|      |      |
|------|------|
| 访问范围 | None |
| 类型 | class |
| 名称 | TopologicalSort |
| 说明 | TopologicalSort类实现图的拓扑排序，计算入度并返回排序后的顶点列表，若图有环则抛出异常。 |


### UML类图

```mermaid
classDiagram
    class TopologicalSort~E~ {
        -AdjacencyList~E~ graph
        -Map~E, Integer~ inDegree
        +TopologicalSort(AdjacencyList~E~ graph)
        +void calculateInDegree()
        +ArrayList~E~ topSortOrder()
    }

    class AdjacencyList~E~ {
        +Set~E~ getVertices()
        +Set~E~ getAdjacents(E vertex)
    }

    TopologicalSort --> AdjacencyList : 依赖
```

这段代码实现了一个拓扑排序算法，用于对有向无环图（DAG）进行排序。`TopologicalSort`类通过`AdjacencyList`类表示图结构，并计算每个顶点的入度。`calculateInDegree`方法计算所有顶点的入度，`topSortOrder`方法使用队列进行拓扑排序，并检测图中是否存在环。如果图中存在环，则抛出`IllegalStateException`异常。


### 内部方法调用关系图

```mermaid
graph TD
    A["类TopologicalSort<E extends Comparable<E>>"]
    B["属性: AdjacencyList<E> graph"]
    C["属性: Map<E, Integer> inDegree"]
    D["构造方法: TopologicalSort(AdjacencyList<E> graph)"]
    E["方法: void calculateInDegree()"]
    F["方法: ArrayList<E> topSortOrder()"]
    G["创建HashMap: inDegree = new HashMap<>()"]
    H["遍历顶点: for (E vertex : graph.getVertices())"]
    I["初始化顶点入度: inDegree.putIfAbsent(vertex, 0)"]
    J["遍历邻接顶点: for (E adjacent : graph.getAdjacents(vertex))"]
    K["更新入度: inDegree.put(adjacent, inDegree.getOrDefault(adjacent, 0) + 1)"]
    L["调用calculateInDegree()"]
    M["创建队列: Queue<E> q = new LinkedList<>()"]
    N["遍历入度表: for (var entry : inDegree.entrySet())"]
    O["添加入度为0的顶点: q.add(entry.getKey())"]
    P["创建结果列表: ArrayList<E> answer = new ArrayList<>()"]
    Q["初始化已处理顶点数: int processedVertices = 0"]
    R["处理队列: while (!q.isEmpty())"]
    S["取出顶点: E current = q.poll()"]
    T["添加到结果列表: answer.add(current)"]
    U["增加已处理顶点数: processedVertices++"]
    V["遍历邻接顶点: for (E adjacent : graph.getAdjacents(current))"]
    W["更新邻接顶点入度: inDegree.put(adjacent, inDegree.get(adjacent) - 1)"]
    X["添加入度为0的顶点: q.add(adjacent)"]
    Y["检查是否有环: if (processedVertices != graph.getVertices().size())"]
    Z["抛出异常: throw new IllegalStateException('Graph contains a cycle, topological sort not possible')"]
    AA["返回结果列表: return answer"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    E --> G
    E --> H
    H --> I
    H --> J
    J --> K
    F --> L
    F --> M
    F --> N
    N --> O
    F --> P
    F --> Q
    F --> R
    R --> S
    S --> T
    T --> U
    U --> V
    V --> W
    W --> X
    F --> Y
    Y --> Z
    F --> AA
```

**描述：**  
这段代码实现了一个拓扑排序算法，用于对有向无环图（DAG）进行排序。首先，通过`calculateInDegree`方法计算每个顶点的入度，然后使用`topSortOrder`方法进行拓扑排序。排序过程中，使用队列存储入度为0的顶点，并逐步处理这些顶点及其邻接顶点，更新入度并将新的入度为0的顶点加入队列。如果最终处理的顶点数与图中顶点总数不一致，则抛出异常，表示图中存在环，无法进行拓扑排序。最终返回排序后的顶点列表。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| inDegree | Map<E, Integer> | 存储元素E及其入度的映射关系。 |
| graph | AdjacencyList<E> | AdjacencyList<E> 表示图数据结构，使用邻接表存储元素E的节点关系。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| calculateInDegree | void | 计算图中每个顶点的入度并存储在HashMap中。 |
| topSortOrder | ArrayList<E> | 该方法实现图的拓扑排序，通过入度计算和队列处理，确保无环图的有序排列。 |



## 类 KahnsAlgorithm

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | KahnsAlgorithm |
| 说明 | Kahn算法实现图的拓扑排序，输出节点顺序。 |


### UML类图

```mermaid
classDiagram
    class KahnsAlgorithm {
        -KahnsAlgorithm()
        +main(String[] args)
    }

    class AdjacencyList~T~ {
        +addEdge(T source, T destination)
    }

    class TopologicalSort~T~ {
        +TopologicalSort(AdjacencyList~T~ graph)
        +List~T~ topSortOrder()
    }

    KahnsAlgorithm --> AdjacencyList~String~ : 依赖
    KahnsAlgorithm --> TopologicalSort~String~ : 依赖
    TopologicalSort~T~ --> AdjacencyList~T~ : 依赖
```

类图描述：
`KahnsAlgorithm` 是一个不可继承的类，包含一个私有的构造函数和一个公有的 `main` 方法。`AdjacencyList` 是一个泛型类，提供了 `addEdge` 方法用于添加图的边。`TopologicalSort` 也是一个泛型类，接受 `AdjacencyList` 作为参数，并提供了 `topSortOrder` 方法用于返回拓扑排序的结果。`KahnsAlgorithm` 类依赖于 `AdjacencyList` 和 `TopologicalSort` 类来实现图的拓扑排序功能。


### 内部方法调用关系图

```mermaid
graph TD
    A["类KahnsAlgorithm"]
    B["构造方法: KahnsAlgorithm()"]
    C["main方法: main(String[] args)"]
    D["初始化图: AdjacencyList<String> graph = new AdjacencyList<>()"]
    E["添加边: graph.addEdge('a', 'b')"]
    F["添加边: graph.addEdge('c', 'a')"]
    G["添加边: graph.addEdge('a', 'd')"]
    H["添加边: graph.addEdge('b', 'd')"]
    I["添加边: graph.addEdge('c', 'u')"]
    J["添加边: graph.addEdge('u', 'b')"]
    K["初始化拓扑排序: TopologicalSort<String> topSort = new TopologicalSort<>(graph)"]
    L["遍历并输出拓扑排序结果: for (String s : topSort.topSortOrder())"]
    M["输出: System.out.print(s + ' ')"]

    A --> B
    A -.-> C
    C --> D
    D --> E
    D --> F
    D --> G
    D --> H
    D --> I
    D --> J
    C --> K
    K --> L
    L --> M
```

**描述：**  
该代码实现了基于Kahn算法的拓扑排序。首先，定义了一个邻接表`AdjacencyList`来表示图结构，并通过`addEdge`方法添加了多条边。接着，使用`TopologicalSort`类对图进行拓扑排序，并遍历输出排序结果。整个过程从图的初始化到拓扑排序的输出，清晰地展示了算法的执行流程。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| main | void | Java程序使用邻接表定义图并执行拓扑排序。 |




