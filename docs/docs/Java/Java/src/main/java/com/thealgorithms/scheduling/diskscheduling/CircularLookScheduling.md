# 基础信息

|      |      |
|------|------|
| 名称 | CircularLookScheduling |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/scheduling/diskscheduling/CircularLookScheduling.java |
| 包名 | com.thealgorithms.scheduling.diskscheduling |
| 依赖项 | ['java.util.ArrayList', 'java.util.Collections', 'java.util.List'] |
| 概述说明 | CircularLookScheduling类实现磁盘调度，按方向排序处理请求。 |

# 说明

CircularLookScheduling类实现了磁盘调度算法，主要用于处理磁盘请求并按照特定方向进行排序。该算法通过优化请求的顺序，减少磁头移动距离，从而提高磁盘访问效率。它结合了循环扫描和查找策略，确保在处理请求时兼顾响应时间和系统性能。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| CircularLookScheduling | class | CircularLookScheduling类实现磁盘调度算法，处理请求并按方向排序。 |



## 类 CircularLookScheduling

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | CircularLookScheduling |
| 说明 | CircularLookScheduling类实现磁盘调度算法，处理请求并按方向排序。 |


### UML类图

```mermaid
classDiagram
    class CircularLookScheduling {
        -int currentPosition
        -boolean movingUp
        -int maxCylinder
        +CircularLookScheduling(int startPosition, boolean movingUp, int maxCylinder)
        +List~Integer~ execute(List~Integer~ requests)
        +int getCurrentPosition()
        +boolean isMovingUp()
    }
```

**描述：**  
`CircularLookScheduling` 类实现了一个循环LOOK调度算法，用于处理磁盘请求调度。该类维护当前磁头位置 (`currentPosition`)、移动方向 (`movingUp`) 和最大柱面数 (`maxCylinder`)。`execute` 方法根据当前移动方向处理请求列表，返回按调度顺序排列的请求列表。该类还提供了获取当前磁头位置和移动方向的方法。


### 内部方法调用关系图

```mermaid
graph TD
    A["类CircularLookScheduling"]
    B["属性: int currentPosition"]
    C["属性: boolean movingUp"]
    D["属性: int maxCylinder"]
    E["构造方法: CircularLookScheduling(int startPosition, boolean movingUp, int maxCylinder)"]
    F["方法: List<Integer> execute(List<Integer> requests)"]
    G["方法: int getCurrentPosition()"]
    H["方法: boolean isMovingUp()"]
    I["初始化: currentPosition = startPosition"]
    J["初始化: movingUp = movingUp"]
    K["初始化: maxCylinder = maxCylinder"]
    L["创建空列表: result = new ArrayList<>()"]
    M["创建空列表: upRequests = new ArrayList<>()"]
    N["创建空列表: downRequests = new ArrayList<>()"]
    O["遍历请求: for (int request : requests)"]
    P["过滤有效请求: if (request >= 0 && request < maxCylinder)"]
    Q["分类请求: if (request > currentPosition)"]
    R["添加请求到upRequests: upRequests.add(request)"]
    S["分类请求: else if (request < currentPosition)"]
    T["添加请求到downRequests: downRequests.add(request)"]
    U["排序upRequests: Collections.sort(upRequests)"]
    V["排序downRequests: Collections.sort(downRequests)"]
    W["判断方向: if (movingUp)"]
    X["处理向上请求: result.addAll(upRequests)"]
    Y["处理向下请求: result.addAll(downRequests)"]
    Z["处理向下请求: Collections.reverse(downRequests); result.addAll(downRequests)"]
    AA["处理向上请求: Collections.reverse(upRequests); result.addAll(upRequests)"]
    AB["更新当前位置: if (!result.isEmpty()) currentPosition = result.get(result.size() - 1)"]
    AC["返回结果: return result"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    E --> I
    E --> J
    E --> K
    F --> L
    F --> M
    F --> N
    F --> O
    O --> P
    P --> Q
    Q --> R
    P --> S
    S --> T
    F --> U
    F --> V
    F --> W
    W --> X
    X --> Y
    W --> Z
    Z --> AA
    F --> AB
    F --> AC
```

这段代码实现了一个循环LOOK调度算法，用于处理磁盘请求。它根据当前移动方向（向上或向下）对请求进行分类和排序，然后按照顺序处理这些请求，并更新当前位置。代码通过过滤无效请求、分类请求、排序请求以及根据移动方向处理请求来实现调度逻辑，最终返回处理后的请求列表并更新当前位置。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| currentPosition | int | 定义私有整型变量currentPosition。 |
| movingUp | boolean | 布尔变量movingUp用于标识是否向上移动。 |
| maxCylinder | int | 私有整型变量maxCylinder，表示最大气缸数。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getCurrentPosition | int | 获取当前位置的整数值。 |
| execute | List<Integer> | 处理请求列表，按方向过滤排序后返回结果并更新当前位置。 |
| isMovingUp | boolean | 方法`isMovingUp`返回布尔值`movingUp`，表示是否向上移动。 |




