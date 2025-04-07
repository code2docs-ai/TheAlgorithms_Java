# 基础信息

|      |      |
|------|------|
| 名称 | EggDropping |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming/EggDropping.java |
| 包名 | com.thealgorithms.dynamicprogramming |
| 依赖项 | [] |
| 概述说明 | EggDropping类用动态规划计算n蛋m楼最小试验次数。 |

# 说明

EggDropping类使用动态规划方法，计算在给定n个鸡蛋和m层楼的情况下，确定最小试验次数的算法。该方法通过构建一个二维表，逐步填充每个子问题的解，最终得出在最坏情况下所需的最少试验次数，以确保找到鸡蛋从哪一层楼开始摔碎的关键楼层。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| EggDropping | class | EggDropping类通过动态规划计算n个鸡蛋和m层楼的最小试验次数。 |



## 类 EggDropping

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | EggDropping |
| 说明 | EggDropping类通过动态规划计算n个鸡蛋和m层楼的最小试验次数。 |


### UML类图

```mermaid
classDiagram
    class EggDropping {
        +EggDropping()
        +int minTrials(int n, int m)
        +void main(String[] args)
    }
```

```mermaid
flowchart TD
    A["开始"] --> B["初始化 eggFloor 数组"]
    B --> C["设置 eggFloor[i][0] = 0"]
    C --> D["设置 eggFloor[i][1] = 1"]
    D --> E["设置 eggFloor[1][j] = j"]
    E --> F["使用动态规划填充 eggFloor 数组"]
    F --> G["选择最小的结果"]
    G --> H["返回 eggFloor[n][m]"]
    H --> I["结束"]
```

```mermaid
sequenceDiagram
    participant Main as main
    participant EggDropping as EggDropping
    Main->>EggDropping: minTrials(2, 4)
    EggDropping->>EggDropping: 初始化 eggFloor 数组
    EggDropping->>EggDropping: 设置 eggFloor[i][0] = 0
    EggDropping->>EggDropping: 设置 eggFloor[i][1] = 1
    EggDropping->>EggDropping: 设置 eggFloor[1][j] = j
    EggDropping->>EggDropping: 使用动态规划填充 eggFloor 数组
    EggDropping->>EggDropping: 选择最小的结果
    EggDropping->>Main: 返回 eggFloor[n][m]
```

**描述：**
`EggDropping` 类用于解决经典的鸡蛋掉落问题，通过动态规划方法计算在最坏情况下确定鸡蛋从哪一层楼掉下不会碎的最小试验次数。代码初始化一个二维数组 `eggFloor`，并通过自底向上的方式填充数组，最终返回在给定鸡蛋数量和楼层数下的最小试验次数。


### 内部方法调用关系图

```mermaid
graph TD
    A["类EggDropping"]
    B["私有构造方法: EggDropping()"]
    C["静态方法: int minTrials(int n, int m)"]
    D["main方法: main(String[] args)"]
    E["初始化二维数组: int[][] eggFloor = new int[n + 1][m + 1]"]
    F["变量声明: int result, int x"]
    G["初始化eggFloor[i][0] = 0, eggFloor[i][1] = 1"]
    H["初始化eggFloor[1][j] = j"]
    I["动态规划填充eggFloor[i][j]"]
    J["返回eggFloor[n][m]"]
    K["调用minTrials(n, m)"]
    L["输出结果: System.out.println(result)"]

    A --> B
    A --> C
    A --> D
    C --> E
    C --> F
    C --> G
    C --> H
    C --> I
    C --> J
    D --> K
    K --> L
```

这段代码实现了一个经典的“鸡蛋掉落”问题，使用动态规划来计算在最坏情况下，给定`n`个鸡蛋和`m`层楼时，找到临界楼层所需的最少试验次数。代码通过初始化一个二维数组`eggFloor`，并使用动态规划的方法逐步填充该数组，最终返回`eggFloor[n][m]`作为结果。`main`方法中调用`minTrials`并输出结果。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| minTrials | int | 动态规划计算鸡蛋掉落最小试验次数。 |
| main | void | 计算n个鸡蛋和m层楼在最坏情况下的最少试验次数。 |




