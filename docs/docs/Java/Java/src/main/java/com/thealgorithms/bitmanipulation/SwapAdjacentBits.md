# 基础信息

|      |      |
|------|------|
| 名称 | SwapAdjacentBits |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/bitmanipulation/SwapAdjacentBits.java |
| 包名 | com.thealgorithms.bitmanipulation |
| 依赖项 | [] |
| 概述说明 | 交换整数相邻位，使用掩码和位移操作完成。 |

# 说明

该方法通过使用掩码和位移操作来交换整数的相邻位。具体步骤包括：首先，创建掩码以提取奇数位和偶数位；然后，通过位移操作将奇数位和偶数位分别移动到对方的位置；最后，将移动后的位重新组合，完成相邻位的交换。此方法高效且适用于需要快速交换整数相邻位的场景。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| SwapAdjacentBits | class | 交换整数相邻位，通过掩码和位移实现。 |



## 类 SwapAdjacentBits

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | SwapAdjacentBits |
| 说明 | 交换整数相邻位，通过掩码和位移实现。 |


### UML类图

```mermaid
classDiagram
    class SwapAdjacentBits {
        -SwapAdjacentBits()
        +int swapAdjacentBits(int num)
    }
```

```mermaid
flowchart TD
    A["开始"] --> B["获取输入整数 num"]
    B --> C["掩码偶数位: evenBits = num & 0xAAAAAAAA"]
    C --> D["掩码奇数位: oddBits = num & 0x55555555"]
    D --> E["右移偶数位: evenBits >>= 1"]
    E --> F["左移奇数位: oddBits <<= 1"]
    F --> G["合并移位后的位: return evenBits | oddBits"]
    G --> H["结束"]
```

```mermaid
sequenceDiagram
    participant User
    participant SwapAdjacentBits
    User ->> SwapAdjacentBits: swapAdjacentBits(num)
    SwapAdjacentBits ->> SwapAdjacentBits: evenBits = num & 0xAAAAAAAA
    SwapAdjacentBits ->> SwapAdjacentBits: oddBits = num & 0x55555555
    SwapAdjacentBits ->> SwapAdjacentBits: evenBits >>= 1
    SwapAdjacentBits ->> SwapAdjacentBits: oddBits <<= 1
    SwapAdjacentBits ->> SwapAdjacentBits: return evenBits | oddBits
    SwapAdjacentBits -->> User: 返回结果
```

**描述：**  
`SwapAdjacentBits` 类提供了一个静态方法 `swapAdjacentBits`，用于交换整数中相邻的位。该方法通过掩码操作分别提取偶数和奇数位，然后通过移位操作交换它们的位置，最后将移位后的位合并返回。类图展示了类的结构，流程图和时序图分别描述了方法的执行流程和调用顺序。


### 内部方法调用关系图

```mermaid
graph TD
    A["类SwapAdjacentBits"]
    B["私有构造方法: SwapAdjacentBits()"]
    C["静态方法: swapAdjacentBits(int num)"]
    D["步骤1: 掩码偶数位 (num & 0xAAAAAAAA)"]
    E["步骤2: 掩码奇数位 (num & 0x55555555)"]
    F["步骤3: 右移偶数位 (evenBits >>= 1)"]
    G["步骤3: 左移奇数位 (oddBits <<= 1)"]
    H["步骤4: 合并移位后的位 (evenBits | oddBits)"]

    A --> B
    A --> C
    C --> D
    C --> E
    C --> F
    C --> G
    C --> H
```

这段代码定义了一个名为 `SwapAdjacentBits` 的类，其中包含一个静态方法 `swapAdjacentBits`，用于交换给定整数的相邻位。方法首先通过掩码操作分离出偶数位和奇数位，然后分别对它们进行右移和左移操作，最后将移位后的位合并返回结果。该代码通过位操作高效地实现了相邻位的交换。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| swapAdjacentBits | int | 交换整数相邻位的函数，通过掩码和位移实现。 |




