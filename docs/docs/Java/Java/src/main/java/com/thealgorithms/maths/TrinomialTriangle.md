# 基础信息

|      |      |
|------|------|
| 名称 | TrinomialTriangle |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/maths/TrinomialTriangle.java |
| 包名 | com.thealgorithms.maths |
| 依赖项 | [] |
| 概述说明 | TrinomialTriangle类实现三项式三角形计算与打印。 |

# 说明

TrinomialTriangle类专门用于计算和打印三项式三角形。该类通过实现核心算法，能够高效生成三项式三角形的各项数值，并提供了打印功能，以便用户能够直观地查看三角形的结构。该类的设计旨在简化三项式三角形的生成和展示过程，适用于需要此类计算的数学和编程场景。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| TrinomialTriangle | class | TrinomialTriangle类实现三项式三角形计算与打印功能。 |



## 类 TrinomialTriangle

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | TrinomialTriangle |
| 说明 | TrinomialTriangle类实现三项式三角形计算与打印功能。 |


### UML类图

```mermaid
classDiagram
    class TrinomialTriangle {
        +TrinomialTriangle()
        +int trinomialValue(int n, int k)
        +void printTrinomial(int n)
        +void main(String[] argc)
    }
```

```mermaid
flowchart TD
    A["开始"] --> B["初始化 n = 6"]
    B --> C["调用 printTrinomial(n)"]
    C --> D["循环 i 从 0 到 n-1"]
    D --> E["循环 j 从 -i 到 0"]
    E --> F["调用 trinomialValue(i, j)"]
    F --> G["输出 trinomialValue(i, j)"]
    G --> H["循环 j 从 1 到 i"]
    H --> I["调用 trinomialValue(i, j)"]
    I --> J["输出 trinomialValue(i, j)"]
    J --> K["换行"]
    K --> L{"i < n-1?"}
    L -- 是 --> D
    L -- 否 --> M["结束"]
```

```mermaid
sequenceDiagram
    participant Main as main
    participant Print as printTrinomial
    participant Value as trinomialValue

    Main->>Print: printTrinomial(n)
    loop i from 0 to n-1
        Print->>Value: trinomialValue(i, j)
        Value-->>Print: 返回值
        Print->>Value: trinomialValue(i, j)
        Value-->>Print: 返回值
        Print->>Print: 输出并换行
    end
    Print-->>Main: 完成
```

**描述**：`TrinomialTriangle` 类包含三个方法：`trinomialValue` 用于计算三项式系数，`printTrinomial` 用于打印三项式三角形，`main` 方法用于启动程序。流程图展示了程序的执行顺序，时序图展示了方法之间的调用关系。


### 内部方法调用关系图

```mermaid
graph TD
    A["类TrinomialTriangle"]
    B["私有构造方法: TrinomialTriangle()"]
    C["静态方法: int trinomialValue(int n, int k)"]
    D["条件判断: n == 0 && k == 0"]
    E["返回: 1"]
    F["条件判断: k < -n || k > n"]
    G["返回: 0"]
    H["递归调用: trinomialValue(n - 1, k - 1) + trinomialValue(n - 1, k) + trinomialValue(n - 1, k + 1)"]
    I["静态方法: void printTrinomial(int n)"]
    J["循环: for (int i = 0; i < n; i++)"]
    K["循环: for (int j = -i; j <= 0; j++)"]
    L["输出: System.out.print(trinomialValue(i, j) + ' ')"]
    M["循环: for (int j = 1; j <= i; j++)"]
    N["输出: System.out.print(trinomialValue(i, j) + ' ')"]
    O["输出换行: System.out.println()"]
    P["main方法: main(String[] argc)"]
    Q["调用: printTrinomial(n)"]

    A --> B
    A --> C
    A --> I
    A -.-> P
    C --> D
    C --> F
    C --> H
    D --> E
    F --> G
    I --> J
    J --> K
    K --> L
    J --> M
    M --> N
    J --> O
    P --> Q
```

这段代码定义了一个名为`TrinomialTriangle`的类，该类包含一个私有的构造方法和三个静态方法。`trinomialValue`方法用于计算三叉树的值，`printTrinomial`方法用于打印三叉树的结构，`main`方法则调用`printTrinomial`方法来展示结果。代码通过递归和循环实现了三叉树的计算和打印功能。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| printTrinomial | void | 打印三叉树数值，按行输出。 |
| trinomialValue | int | 递归计算三项式系数，边界条件返回1或0。 |
| main | void | Java主方法调用打印三项式函数，参数n为6。 |




