# 基础信息

|      |      |
|------|------|
| 名称 | graphs |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/datastructures/graphs |
| 包名 | Java.src.main.java.com.thealgorithms.datastructures.graphs |
| 概述说明 | 多种图算法实现，包括最短路径、最小生成树、环检测、拓扑排序等。 |

# 说明

## 概述

该代码模块主要实现了图论中的多种经典算法和数据结构，涵盖了图的表示、遍历、最短路径计算、最小生成树、最大流、强连通分量、拓扑排序、二分图检测、图着色、环检测、哈密顿环检测等功能。这些算法和数据结构通过不同的类实现，提供了对图结构的全面管理和分析能力，适用于各种图相关的应用场景。

## 主要业务场景

1. **最短路径计算**：
   - **Bellman-Ford算法**：用于检测图中是否存在负权环，并计算各顶点之间的最短路径。
   - **Dijkstra算法**：计算从源点到各顶点的最短路径，适用于非负权图。
   - **Dijkstra优化算法**：通过减少不必要的计算和存储开销，提高Dijkstra算法的效率。
   - **Johnson算法**：结合Bellman-Ford和Dijkstra算法，计算所有顶点对之间的最短路径，适用于包含负权边的图。
   - **Floyd-Warshall算法**：计算图中所有顶点对之间的最短路径，适用于包含负权边的图。

2. **最小生成树**：
   - **Prim算法**：通过贪心策略求解无向连通图的最小生成树。
   - **Kruskal算法**：通过优先队列和并查集数据结构构建最小生成树。
   - **Boruvka算法**：通过并查集操作和状态管理求解最小生成树。

3. **最大流**：
   - **Ford-Fulkerson算法**：通过寻找增广路径计算网络的最大流。

4. **强连通分量**：
   - **Tarjan算法**：通过深度优先搜索和栈结构查找有向图中的强连通分量。
   - **Kosaraju算法**：通过深度优先搜索和图的转置查找有向图中的强连通分量。

5. **拓扑排序**：
   - **Kahn算法**：通过计算顶点的入度实现图的拓扑排序。
   - **TopologicalSort类**：提供图的拓扑排序功能。

6. **二分图检测**：
   - **BipartiteGraphDFS类**：使用深度优先搜索验证图是否为二分图。

7. **图着色**：
   - **WelshPowell类**：实现图着色算法，确保相邻节点颜色不同。

8. **环检测**：
   - **Cycle类**：通过深度优先搜索检测图中的所有环。
   - **HamiltonianCycle类**：通过递归方法检测图中的哈密顿环。

9. **图的基本操作**：
   - **AdjacencyListGraph类**：实现基于邻接表的图结构，支持添加和删除边与顶点。
   - **MatrixGraphs类**：实现图的邻接矩阵表示，支持深度优先遍历和广度优先遍历。
   - **UndirectedAdjacencyListGraph类**：提供无向图的管理和操作功能。

10. **连通组件**：
    - **ConnectedComponent类**：用于创建和统计图中的连通组件数量。

11. **最大匹配**：
    - **Edmonds Blossom算法**：通过广度优先搜索和花收缩技术解决图的最大匹配问题。

12. **A*算法**：
    - **AStar类**：实现A*算法，用于在图中查找最短路径。

该模块通过多种算法和数据结构的实现，提供了对图结构的全面支持，适用于从最短路径计算到图结构分析的多种业务场景。


### 包内部结构视图

```mermaid
graph TD
    graphs --> BellmanFord.java
    graphs --> MatrixGraphs.java
    graphs --> JohnsonsAlgorithm.java
    graphs --> UndirectedAdjacencyListGraph.java
    graphs --> TarjansAlgorithm.java
    graphs --> FordFulkerson.java
    graphs --> EdmondsBlossomAlgorithm.java
    graphs --> Kosaraju.java
    graphs --> WelshPowell.java
    graphs --> ConnectedComponent.java
    graphs --> AStar.java
    graphs --> BipartiteGraphDFS.java
    graphs --> PrimMST.java
    graphs --> BoruvkaAlgorithm.java
    graphs --> DijkstraOptimizedAlgorithm.java
    graphs --> FloydWarshall.java
    graphs --> KahnsAlgorithm.java
    graphs --> Graphs.java
    graphs --> Cycles.java
    graphs --> Kruskal.java
    graphs --> HamiltonianCycle.java
    graphs --> DijkstraAlgorithm.java
```

该流程图展示了`graphs`文件夹下的所有Java文件，这些文件实现了不同的图算法。每个文件都直接依赖于`graphs`文件夹，形成了一个简单的层级结构。这种结构有助于快速识别和管理各种图算法的实现。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [HamiltonianCycle.java](HamiltonianCycle.md) | file | HamiltonianCycle类递归搜索邻接矩阵寻找哈密顿环，找到返回顶点序列，否则返回-1。 |
| [Cycles.java](Cycles.md) | file | Cycle类通过DFS检测图中的环，Cycles类调用其方法并输出结果。 |
| [BoruvkaAlgorithm.java](BoruvkaAlgorithm.md) | file | Boruvka算法实现最小生成树，涉及图结构、边定义、并查集操作及状态管理。 |
| [AStar.java](AStar.md) | file | AStar类实现A*算法，用于图中最短路径搜索，包含图结构、边和路径信息，使用优先队列探索节点。 |
| [WelshPowell.java](WelshPowell.md) | file | WelshPowell算法实现图着色，邻接表表示图，按度排序并分配颜色。 |
| [TarjansAlgorithm.java](TarjansAlgorithm.md) | file | Tarjan算法用于查找有向图的强连通分量。 |
| [BellmanFord.java](BellmanFord.md) | file | BellmanFord算法检测负权环，计算并输出最短路径，支持边和顶点输入。 |
| [Kruskal.java](Kruskal.md) | file | Kruskal算法利用优先队列排序边，合并连通组件避免环路生成最小生成树。 |
| [Graphs.java](Graphs.md) | file | AdjacencyListGraph类实现图结构，支持边和顶点操作，Graphs类测试添加边功能。 |
| [DijkstraAlgorithm.java](DijkstraAlgorithm.md) | file | Dijkstra算法用于计算图中源点到各顶点的最短路径。 |
| [KahnsAlgorithm.java](KahnsAlgorithm.md) | file | 实现有向图邻接表，支持添加边、获取邻接顶点和所有顶点。提供拓扑排序功能，使用Kahn算法，检测环并返回排序结果。 |
| [FloydWarshall.java](FloydWarshall.md) | file | FloydWarshall类实现Floyd-Warshall算法，计算所有顶点对的最短路径并输出距离矩阵。 |
| [DijkstraOptimizedAlgorithm.java](DijkstraOptimizedAlgorithm.md) | file | Dijkstra算法优化，利用邻接矩阵求源点到各顶点最短路径。 |
| [PrimMST.java](PrimMST.md) | file | Prim算法利用邻接矩阵实现最小生成树。 |
| [BipartiteGraphDFS.java](BipartiteGraphDFS.md) | file | BipartiteGraphDFS类利用DFS算法验证图的二分性，确保相邻节点颜色互异。 |
| [ConnectedComponent.java](ConnectedComponent.md) | file | 图类管理节点和边，ConnectedComponent类统计字符与整数图数量。 |
| [Kosaraju.java](Kosaraju.md) | file | Kosaraju算法通过DFS排序、转置图和寻找强连通分量实现。 |
| [EdmondsBlossomAlgorithm.java](EdmondsBlossomAlgorithm.md) | file | Edmonds Blossom算法利用BFS和花收缩实现图的最大匹配。 |
| [FordFulkerson.java](FordFulkerson.md) | file | Ford-Fulkerson算法用于计算网络中的最大流量。 |
| [UndirectedAdjacencyListGraph.java](UndirectedAdjacencyListGraph.md) | file | 无向图类支持节点、边操作，可获取邻居、边权重及节点数量。 |
| [JohnsonsAlgorithm.java](JohnsonsAlgorithm.md) | file | Johnson算法结合Bellman-Ford和Dijkstra计算图顶点对最短路径。 |
| [MatrixGraphs.java](MatrixGraphs.md) | file | MatrixGraphs类创建10节点图，管理边并输出深度和广度优先遍历结果。AdjacencyMatrixGraph类实现邻接矩阵表示，支持顶点和边管理，提供两种遍历方法。 |


