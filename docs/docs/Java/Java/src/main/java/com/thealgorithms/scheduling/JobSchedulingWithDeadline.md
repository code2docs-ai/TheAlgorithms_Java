# 基础信息

|      |      |
|------|------|
| 名称 | JobSchedulingWithDeadline |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/scheduling/JobSchedulingWithDeadline.java |
| 包名 | com.thealgorithms.scheduling |
| 依赖项 | ['java.util.Arrays', 'java.util.Comparator'] |
| 概述说明 | JobSchedulingWithDeadline类按利润最大化调度任务，考虑到达和截止时间。 |

# 说明

类JobSchedulingWithDeadline包含一个内部类Job和一个方法jobSequencingWithDeadlines。该类的目的是通过调度任务来实现利润最大化，同时考虑每个任务的到达时间和截止时间。Job类用于定义任务的基本属性，而jobSequencingWithDeadlines方法则负责根据这些属性对任务进行排序和调度，以确保在截止时间前完成并最大化总利润。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| JobSchedulingWithDeadline | class | 类JobSchedulingWithDeadline包含Job类和方法jobSequencingWithDeadlines，用于按利润最大化调度任务，考虑到达时间和截止时间。 |



## 类 JobSchedulingWithDeadline

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | JobSchedulingWithDeadline |
| 说明 | 类JobSchedulingWithDeadline包含Job类和方法jobSequencingWithDeadlines，用于按利润最大化调度任务，考虑到达时间和截止时间。 |


### UML类图

```mermaid
classDiagram
    class JobSchedulingWithDeadline {
        +JobSchedulingWithDeadline()
        +int[] jobSequencingWithDeadlines(Job[] jobs)
    }

    class Job {
        -int jobId
        -int arrivalTime
        -int deadline
        -int profit
        +Job(int jobId, int arrivalTime, int deadline, int profit)
    }

    JobSchedulingWithDeadline --> Job : 依赖
```

### 描述
`JobSchedulingWithDeadline` 是一个用于调度作业以最大化利润的类，考虑了作业的到达时间和截止时间。它包含一个内部类 `Job`，用于表示作业的ID、到达时间、截止时间和利润。`jobSequencingWithDeadlines` 方法通过按利润降序排序作业，并尝试在截止时间之前分配时间槽来调度作业，最终返回成功调度的作业数量和总利润。


### 内部方法调用关系图

```mermaid
graph TD
    A["类JobSchedulingWithDeadline"]
    B["静态内部类Job"]
    C["属性: int jobId"]
    D["属性: int arrivalTime"]
    E["属性: int deadline"]
    F["属性: int profit"]
    G["构造方法: Job(int jobId, int arrivalTime, int deadline, int profit)"]
    H["静态方法: jobSequencingWithDeadlines(Job[] jobs)"]
    I["排序: Arrays.sort(jobs, Comparator.comparingInt(job -> - job.profit))"]
    J["计算最大截止时间: int maxDeadline = Arrays.stream(jobs).mapToInt(job -> job.deadline).max().orElse(0)"]
    K["初始化时间槽: int[] timeSlots = new int[maxDeadline]"]
    L["填充时间槽: Arrays.fill(timeSlots, -1)"]
    M["初始化计数器和利润: int count = 0, int maxProfit = 0"]
    N["调度作业: for (Job job : jobs)"]
    O["检查到达时间: if (job.arrivalTime <= job.deadline)"]
    P["分配时间槽: for (int i = Math.min(job.deadline - 1, maxDeadline - 1); i >= job.arrivalTime - 1; i--)"]
    Q["检查时间槽是否空闲: if (timeSlots[i] == -1)"]
    R["分配作业: timeSlots[i] = job.jobId"]
    S["更新计数器和利润: count++, maxProfit += job.profit"]
    T["返回结果: return new int[] {count, maxProfit}"]

    A --> B
    B --> C
    B --> D
    B --> E
    B --> F
    B --> G
    A --> H
    H --> I
    H --> J
    H --> K
    H --> L
    H --> M
    H --> N
    N --> O
    O --> P
    P --> Q
    Q --> R
    R --> S
    H --> T
```

这段代码实现了一个作业调度算法，目的是在满足作业的到达时间和截止时间的前提下，最大化利润。代码首先对作业按利润降序排序，然后根据作业的截止时间和到达时间，将作业分配到时间槽中。最终返回成功调度的作业数量和总利润。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| jobSequencingWithDeadlines | int[] | 按利润排序任务，安排任务以最大化收益。 |




