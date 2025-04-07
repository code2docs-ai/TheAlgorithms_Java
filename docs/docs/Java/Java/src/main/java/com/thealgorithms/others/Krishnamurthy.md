# 基础信息

|      |      |
|------|------|
| 名称 | Krishnamurthy |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/others/Krishnamurthy.java |
| 包名 | com.thealgorithms.others |
| 依赖项 | ['java.util.Scanner'] |
| 概述说明 | Krishnamurthy类用于判断输入数字是否为Krishnamurthy数。 |

# 说明

Krishnamurthy类用于判断输入的数字是否为Krishnamurthy数。Krishnamurthy数是指一个数字等于其各位数字的阶乘之和。例如，145是一个Krishnamurthy数，因为1! + 4! + 5! = 1 + 24 + 120 = 145。该类通过计算输入数字的每一位数字的阶乘并求和，最后将结果与原始数字进行比较，以确定其是否为Krishnamurthy数。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| Krishnamurthy | class | Krishnamurthy类判断输入数字是否为Krishnamurthy数。 |



## 类 Krishnamurthy

|      |      |
|------|------|
| 访问范围 | final |
| 类型 | class |
| 名称 | Krishnamurthy |
| 说明 | Krishnamurthy类判断输入数字是否为Krishnamurthy数。 |


### UML类图

```mermaid
classDiagram
    class Krishnamurthy {
        +Krishnamurthy()
        +static int fact(int n)
        +static void main(String[] args)
    }
```

```mermaid
flowchart TD
    A["开始"] --> B["Scanner sc = new Scanner(System.in)"]
    B --> C["System.out.print('Enter the number : ')"]
    C --> D["int a = sc.nextInt()"]
    D --> E["int n = a"]
    E --> F["int s = 0"]
    F --> G{"a > 0?"}
    G -- 是 --> H["int b = a % 10"]
    H --> I["s = s + fact(b)"]
    I --> J["a = a / 10"]
    J --> G
    G -- 否 --> K{"s == n?"}
    K -- 是 --> L["System.out.print(n + ' is a krishnamurthy number')"]
    K -- 否 --> M["System.out.print(n + ' is not a krishnamurthy number')"]
    L --> N["sc.close()"]
    M --> N
    N --> O["结束"]
```

```mermaid
sequenceDiagram
    participant Main as Krishnamurthy
    participant Scanner as Scanner
    participant System as System
    Main ->> Scanner: new Scanner(System.in)
    Main ->> System: print("Enter the number : ")
    Main ->> Scanner: nextInt()
    Main ->> Main: fact(b)
    Main ->> System: print(n + " is a krishnamurthy number")
    Main ->> System: print(n + " is not a krishnamurthy number")
    Main ->> Scanner: close()
```

**描述：**  
该代码定义了一个名为 `Krishnamurthy` 的最终类，包含一个私有构造函数和两个静态方法。`fact` 方法用于计算给定整数的阶乘，`main` 方法则通过用户输入的数字判断其是否为 Krishnamurthy 数（即其各位数字的阶乘之和等于该数本身）。流程图展示了程序的执行流程，时序图则描述了类与外部系统（如 `Scanner` 和 `System`）之间的交互过程。


### 内部方法调用关系图

```mermaid
graph TD
    A["类Krishnamurthy"]
    B["私有构造方法: Krishnamurthy()"]
    C["静态方法: int fact(int n)"]
    D["main方法: main(String[] args)"]
    E["创建Scanner对象: Scanner sc = new Scanner(System.in)"]
    F["输出提示: 'Enter the number : '"]
    G["读取输入: a = sc.nextInt()"]
    H["初始化变量: int n = a, int s = 0"]
    I["循环: while (a > 0)"]
    J["计算个位数: b = a % 10"]
    K["累加阶乘: s = s + fact(b)"]
    L["更新a: a = a / 10"]
    M["判断是否为Krishnamurthy数: if (s == n)"]
    N["输出结果: n + ' is a krishnamurthy number'"]
    O["输出结果: n + ' is not a krishnamurthy number'"]
    P["关闭Scanner: sc.close()"]

    A --> B
    A --> C
    A --> D
    D --> E
    D --> F
    D --> G
    D --> H
    D --> I
    I --> J
    I --> K
    I --> L
    I --> M
    M --> N
    M --> O
    D --> P
```

这段代码定义了一个名为`Krishnamurthy`的类，用于判断一个数是否为Krishnamurthy数（即一个数的各位数字的阶乘之和等于它本身）。代码首先通过`Scanner`获取用户输入的数字，然后通过循环计算该数字的各位数字的阶乘并累加，最后判断累加结果是否与原始数字相等，从而输出判断结果。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| fact | int | 计算整数n的阶乘并返回结果。 |
| main | void | Java程序判断输入数字是否为Krishnamurthy数。 |




