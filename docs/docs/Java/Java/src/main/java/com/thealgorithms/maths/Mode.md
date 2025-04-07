# 基础信息

|      |      |
|------|------|
| 名称 | Mode |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/maths/Mode.java |
| 包名 | com.thealgorithms.maths |
| 依赖项 | ['java.util.ArrayList', 'java.util.Collections', 'java.util.HashMap'] |
| 概述说明 | 计算数组众数，返回频次最高数。 |

# 说明

该内容描述了一个计算整数数组众数的方法，旨在找出数组中出现次数最多的数。众数是指在数据集中出现频率最高的元素。该方法的实现目标是通过分析数组中的元素频率，确定并返回出现次数最多的那个数。这一过程不涉及具体的代码实现，而是专注于描述其功能目的和核心逻辑。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| Mode | class | 计算整数数组的众数，返回出现次数最多的数。 |



## 类 Mode

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | Mode |
| 说明 | 计算整数数组的众数，返回出现次数最多的数。 |


### UML类图

```mermaid
classDiagram
    class Mode {
        -Mode()
        +int[] mode(int[] numbers)
    }
    class HashMap~K, V~ {
        +boolean containsKey(K key)
        +V get(K key)
        +void put(K key, V value)
    }
    class ArrayList~E~ {
        +void add(E e)
    }
    class Collections {
        +int max(Collection~? extends T~ coll)
    }
    Mode --> HashMap : 依赖
    Mode --> ArrayList : 依赖
    Mode --> Collections : 依赖
```

这段代码定义了一个名为 `Mode` 的类，该类包含一个私有构造函数和一个静态方法 `mode`，用于计算整数数组的众数。`mode` 方法首先检查数组是否为空，然后使用 `HashMap` 统计每个数字的出现次数，接着找到最大出现次数，最后将所有出现次数等于最大值的数字收集到 `ArrayList` 中，并将其转换为数组返回。代码依赖了 `HashMap`、`ArrayList` 和 `Collections` 类来完成这些操作。


### 内部方法调用关系图

```mermaid
graph TD
    A["类Mode"]
    B["私有构造方法: Mode()"]
    C["静态方法: int[] mode(int[] numbers)"]
    D["检查数组长度: if (numbers.length == 0)"]
    E["返回null: return null"]
    F["创建HashMap: HashMap<Integer, Integer> count = new HashMap<>()"]
    G["遍历数组: for (int num : numbers)"]
    H["检查键是否存在: if (count.containsKey(num))"]
    I["更新计数: count.put(num, count.get(num) + 1)"]
    J["初始化计数: count.put(num, 1)"]
    K["获取最大计数值: int max = Collections.max(count.values())"]
    L["创建ArrayList: ArrayList<Integer> modes = new ArrayList<>()"]
    M["遍历HashMap: for (final var entry : count.entrySet())"]
    N["检查计数值是否等于最大值: if (entry.getValue() == max)"]
    O["添加mode到ArrayList: modes.add(entry.getKey())"]
    P["转换为数组: return modes.stream().mapToInt(n -> n).toArray()"]

    A --> B
    A --> C
    C --> D
    D -->|"是"| E
    D -->|"否"| F
    F --> G
    G --> H
    H -->|"是"| I
    H -->|"否"| J
    I --> G
    J --> G
    G --> K
    K --> L
    L --> M
    M --> N
    N -->|"是"| O
    O --> M
    N -->|"否"| M
    M --> P
```

这段代码定义了一个名为`Mode`的类，其中包含一个静态方法`mode`，用于计算整数数组的众数。首先检查数组是否为空，如果为空则返回`null`。接着使用`HashMap`统计每个数字的出现次数，然后找到最大计数值，并将所有出现次数等于最大值的数字添加到`ArrayList`中，最后将其转换为数组返回。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| mode | int[] | 计算数组中出现频率最高的元素并返回。 |




