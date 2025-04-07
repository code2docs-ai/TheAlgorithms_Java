# 基础信息

|      |      |
|------|------|
| 名称 | MaximumSumOfDistinctSubarraysWithLengthK |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/others/MaximumSumOfDistinctSubarraysWithLengthK.java |
| 包名 | com.thealgorithms.others |
| 依赖项 | ['java.util.HashSet', 'java.util.Set'] |
| 概述说明 | 求长度为K且元素互不相同的子数组的最大和。 |

# 说明

该问题要求计算长度为K且元素互不相同的子数组的最大和。具体来说，需要从给定数组中找到所有长度为K的子数组，确保这些子数组中的元素互不相同，然后计算这些子数组的和，最终找出其中的最大值。该问题涉及数组遍历、子数组生成、元素唯一性检查以及求和操作，旨在通过高效算法解决这一组合优化问题。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| MaximumSumOfDistinctSubarraysWithLengthK | class | 计算长度为K且元素互不相同的子数组的最大和。 |



## 类 MaximumSumOfDistinctSubarraysWithLengthK

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | MaximumSumOfDistinctSubarraysWithLengthK |
| 说明 | 计算长度为K且元素互不相同的子数组的最大和。 |


### UML类图

```mermaid
classDiagram
    class MaximumSumOfDistinctSubarraysWithLengthK {
        +MaximumSumOfDistinctSubarraysWithLengthK()
        +long maximumSubarraySum(int k, int... nums)
    }
```

```mermaid
flowchart TD
    A["开始"] --> B["检查 nums.length < k"]
    B -- 是 --> C["返回 0"]
    B -- 否 --> D["初始化 masSum, currentSum, currentSet"]
    D --> E["初始化第一个窗口"]
    E --> F["检查当前窗口是否有重复元素"]
    F -- 是 --> G["更新 masSum"]
    F -- 否 --> H["滑动窗口"]
    H --> I["更新 currentSum"]
    I --> J["检查新窗口是否有重复元素"]
    J -- 是 --> K["更新 currentSet"]
    J -- 否 --> L["继续滑动"]
    K --> M["检查当前窗口是否有重复元素"]
    M -- 是 --> N["更新 masSum"]
    M -- 否 --> H
    L --> H
    H --> O["返回 masSum"]
    O --> P["结束"]
```

```mermaid
sequenceDiagram
    participant A as 调用者
    participant B as MaximumSumOfDistinctSubarraysWithLengthK
    A ->> B: maximumSubarraySum(k, nums)
    B ->> B: 检查 nums.length < k
    B -->> A: 返回 0
    B ->> B: 初始化 masSum, currentSum, currentSet
    B ->> B: 初始化第一个窗口
    B ->> B: 检查当前窗口是否有重复元素
    B -->> B: 更新 masSum
    B ->> B: 滑动窗口
    B ->> B: 更新 currentSum
    B ->> B: 检查新窗口是否有重复元素
    B -->> B: 更新 currentSet
    B ->> B: 检查当前窗口是否有重复元素
    B -->> B: 更新 masSum
    B -->> A: 返回 masSum
```

**描述：**  
`MaximumSumOfDistinctSubarraysWithLengthK` 类包含一个静态方法 `maximumSubarraySum`，用于计算数组中长度为 `k` 且元素互不相同的子数组的最大和。方法首先检查数组长度是否小于 `k`，若是则返回 0。接着初始化变量和第一个窗口，检查窗口内元素是否互不相同，若是则更新最大和。然后通过滑动窗口的方式遍历数组，更新当前和并检查新窗口内的元素是否互不相同，最终返回最大和。


### 内部方法调用关系图

```mermaid
graph TD
    A["类MaximumSumOfDistinctSubarraysWithLengthK"]
    B["构造方法: MaximumSumOfDistinctSubarraysWithLengthK()"]
    C["方法: maximumSubarraySum(int k, int... nums)"]
    D["检查: nums.length < k"]
    E["返回: 0"]
    F["初始化变量: masSum, currentSum, currentSet"]
    G["初始化第一个窗口: for循环"]
    H["更新: currentSum, currentSet"]
    I["检查: currentSet.size() == k"]
    J["更新: masSum"]
    K["滑动窗口: for循环"]
    L["更新: currentSum"]
    M["检查: currentSet.size() < k"]
    N["标记: flag"]
    O["更新: currentSet"]
    P["检查: currentSet.size() == k && masSum < currentSum"]
    Q["更新: masSum"]
    R["返回: masSum"]

    A --> B
    A --> C
    C --> D
    D -->|是| E
    D -->|否| F
    F --> G
    G --> H
    H --> I
    I -->|是| J
    I -->|否| K
    K --> L
    L --> M
    M -->|是| N
    M -->|否| O
    N --> O
    O --> P
    P -->|是| Q
    P -->|否| K
    K --> R
```

这段代码定义了一个类 `MaximumSumOfDistinctSubarraysWithLengthK`，其中包含一个静态方法 `maximumSubarraySum`，用于查找长度为 `k` 的、元素互不相同的子数组的最大和。代码通过滑动窗口技术遍历数组，维护当前窗口的和以及元素集合，并在窗口内元素唯一时更新最大和。如果数组长度小于 `k`，则直接返回 0。流程图展示了方法的执行流程，包括初始化、窗口滑动、元素检查和最大和更新等步骤。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| maximumSubarraySum | long | 计算长度为k的连续子数组的最大和，要求子数组元素互不重复。 |




