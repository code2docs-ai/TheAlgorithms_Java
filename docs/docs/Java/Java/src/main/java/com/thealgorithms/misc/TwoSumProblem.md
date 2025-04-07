# 基础信息

|      |      |
|------|------|
| 名称 | TwoSumProblem |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/misc/TwoSumProblem.java |
| 包名 | com.thealgorithms.misc |
| 依赖项 | ['java.util.HashMap', 'java.util.Optional', 'org.apache.commons.lang3.tuple.Pair'] |
| 概述说明 | TwoSumProblem类提供twoSum方法，查找数组中两数之和等于目标值的索引。 |

# 说明

TwoSumProblem类包含一个名为twoSum的方法，该方法用于在给定数组中查找两个数，使它们的和等于指定的目标值。该方法返回这两个数在数组中的索引。通过遍历数组，twoSum方法能够高效地找到满足条件的数对，并返回它们的索引位置。这一功能在解决与数组和求和相关的问题时非常实用。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| TwoSumProblem | class | TwoSumProblem类提供twoSum方法，查找数组中两数之和等于目标值的索引。 |



## 类 TwoSumProblem

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | TwoSumProblem |
| 说明 | TwoSumProblem类提供twoSum方法，查找数组中两数之和等于目标值的索引。 |


### UML类图

```mermaid
classDiagram
    class TwoSumProblem {
        -TwoSumProblem()
        +Optional~Pair~Integer,Integer~~ twoSum(int[] values, int target)
    }
    class Pair~T, U~ {
        +T first
        +U second
        +static Pair~T, U~ of(T first, U second)
    }
    class Optional~T~ {
        +static Optional~T~ of(T value)
        +static Optional~T~ empty()
    }
    class HashMap~K, V~ {
        +void put(K key, V value)
        +V get(K key)
        +boolean containsKey(K key)
    }
    TwoSumProblem --> HashMap : 依赖
    TwoSumProblem --> Optional : 依赖
    Optional --> Pair : 依赖
```

### 描述
该代码实现了一个名为 `TwoSumProblem` 的类，用于解决两数之和问题。`twoSum` 方法接受一个整数数组和一个目标值，返回两个索引，使得数组中对应元素的和等于目标值。方法内部使用 `HashMap` 来存储数组元素及其索引，通过遍历数组查找满足条件的索引对。`Optional` 用于处理可能不存在解的情况，`Pair` 用于封装返回的索引对。


### 内部方法调用关系图

```mermaid
graph TD
    A["类TwoSumProblem"]
    B["私有构造方法: TwoSumProblem()"]
    C["静态方法: Optional<Pair<Integer, Integer>> twoSum(final int[] values, final int target)"]
    D["创建HashMap: HashMap<Integer, Integer> valueToIndex = new HashMap<>()"]
    E["循环遍历数组: for (int i = 0; i < values.length; i++)"]
    F["计算余数: final var remainder = target - values[i]"]
    G["检查余数是否在HashMap中: if (valueToIndex.containsKey(remainder))"]
    H["返回索引对: return Optional.of(Pair.of(valueToIndex.get(remainder), i))"]
    I["检查当前值是否在HashMap中: if (!valueToIndex.containsKey(values[i]))"]
    J["将当前值及其索引存入HashMap: valueToIndex.put(values[i], i)"]
    K["返回空Optional: return Optional.empty()"]

    A --> B
    A --> C
    C --> D
    C --> E
    E --> F
    E --> G
    G --> H
    G --> I
    I --> J
    E --> K
```

该流程图描述了`TwoSumProblem`类中的`twoSum`方法的执行流程。该方法通过遍历数组并使用`HashMap`来存储已访问过的值及其索引，寻找两个数的和等于目标值的情况。如果找到满足条件的两个数，则返回它们的索引；否则返回空`Optional`。整个流程展示了从初始化到最终返回结果的完整步骤。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| twoSum | Optional<Pair<Integer, Integer>> | 该方法通过哈希表查找数组中两数之和等于目标值的索引。 |




