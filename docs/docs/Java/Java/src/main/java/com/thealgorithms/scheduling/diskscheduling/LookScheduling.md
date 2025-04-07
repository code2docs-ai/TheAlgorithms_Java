# 基础信息

|      |      |
|------|------|
| 名称 | LookScheduling |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/scheduling/diskscheduling/LookScheduling.java |
| 包名 | com.thealgorithms.scheduling.diskscheduling |
| 依赖项 | ['java.util.ArrayList', 'java.util.Collections', 'java.util.List'] |
| 概述说明 | LookScheduling类实现磁盘调度算法，按方向处理请求并返回顺序。 |

# 说明

LookScheduling类用于实现磁盘调度算法，其主要功能是根据指定的方向处理磁盘请求，并返回请求的处理顺序。该类的核心任务是优化磁盘访问顺序，以提高磁盘操作的效率。通过按方向处理请求，LookScheduling类能够有效地减少磁头移动距离，从而提升系统性能。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| LookScheduling | class | LookScheduling类实现磁盘调度算法，按方向处理请求并返回处理顺序。 |



## 类 LookScheduling

|      |      |
|------|------|
| 访问范围 | public |
| 类型 | class |
| 名称 | LookScheduling |
| 说明 | LookScheduling类实现磁盘调度算法，按方向处理请求并返回处理顺序。 |


### UML类图

```mermaid
classDiagram
    class LookScheduling {
        -int maxTrack
        -int currentPosition
        -boolean movingUp
        -int farthestPosition
        +LookScheduling(int startPosition, boolean initialDirection, int maxTrack)
        +List~Integer~ execute(List~Integer~ requests)
        +int getCurrentPosition()
        +boolean isMovingUp()
        +int getFarthestPosition()
    }
```

这段代码实现了一个磁盘调度算法中的LOOK算法。`LookScheduling`类通过`execute`方法处理磁盘请求列表，根据当前磁头位置和移动方向，将请求分为向上和向下两部分进行处理。类中包含了最大磁道数、当前磁头位置、移动方向和最远位置的属性，并通过构造函数初始化这些属性。`execute`方法返回处理请求的顺序，同时更新最远位置和移动方向。其他方法用于获取当前磁头位置、移动方向和最远位置。


### 内部方法调用关系图

```mermaid
graph TD
    A["类LookScheduling"]
    B["属性: int maxTrack"]
    C["属性: int currentPosition"]
    D["属性: boolean movingUp"]
    E["属性: int farthestPosition"]
    F["构造方法: LookScheduling(int startPosition, boolean initialDirection, int maxTrack)"]
    G["方法: List<Integer> execute(List<Integer> requests)"]
    H["方法: int getCurrentPosition()"]
    I["方法: boolean isMovingUp()"]
    J["方法: int getFarthestPosition()"]
    K["局部变量: List<Integer> result"]
    L["局部变量: List<Integer> lower"]
    M["局部变量: List<Integer> upper"]
    N["遍历请求: for (int request : requests)"]
    O["判断请求位置: if (request >= 0 && request < maxTrack)"]
    P["添加到lower或upper: if (request < currentPosition)"]
    Q["排序: Collections.sort(lower)"]
    R["排序: Collections.sort(upper)"]
    S["处理请求: if (movingUp)"]
    T["处理向上请求: result.addAll(upper)"]
    U["更新farthestPosition: farthestPosition = upper.get(upper.size() - 1)"]
    V["反转方向: movingUp = false"]
    W["反转lower: Collections.reverse(lower)"]
    X["处理向下请求: result.addAll(lower)"]
    Y["更新farthestPosition: farthestPosition = Math.max(farthestPosition, lower.get(0))"]
    Z["处理向下请求: Collections.reverse(lower)"]
    AA["处理向下请求: result.addAll(lower)"]
    AB["更新farthestPosition: farthestPosition = lower.get(0)"]
    AC["反转方向: movingUp = true"]
    AD["处理向上请求: result.addAll(upper)"]
    AE["更新farthestPosition: farthestPosition = Math.max(farthestPosition, upper.get(upper.size() - 1))"]
    AF["返回结果: return result"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    A --> I
    A --> J
    G --> K
    G --> L
    G --> M
    G --> N
    N --> O
    O --> P
    G --> Q
    G --> R
    G --> S
    S --> T
    T --> U
    S --> V
    V --> W
    W --> X
    X --> Y
    S --> Z
    Z --> AA
    AA --> AB
    S --> AC
    AC --> AD
    AD --> AE
    G --> AF
```

这段代码实现了一个Look调度算法，用于处理磁盘请求。代码首先根据当前磁头位置将请求分为两部分，然后根据初始移动方向处理这些请求。如果初始方向向上，则先处理上方的请求，再反转方向处理下方的请求；反之亦然。最后返回处理顺序的结果。代码还包含了获取当前磁头位置、移动方向和最远位置的辅助方法。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| maxTrack | int | 私有整型变量maxTrack，用于存储最大轨道数。 |
| movingUp | boolean | 布尔变量movingUp用于控制向上移动状态。 |
| currentPosition | int | 私有整型变量currentPosition。 |
| farthestPosition | int | 私有整型变量，记录最远位置。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| getCurrentPosition | int | 获取当前位置的方法，返回currentPosition值。 |
| getFarthestPosition | int | 获取最远位置的方法。 |
| execute | List<Integer> | 根据请求位置和移动方向处理并排序列表，返回处理结果。 |
| isMovingUp | boolean | 方法isMovingUp返回布尔值movingUp，表示是否向上移动。 |




