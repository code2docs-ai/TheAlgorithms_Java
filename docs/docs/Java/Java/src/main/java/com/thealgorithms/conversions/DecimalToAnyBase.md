# 基础信息

|      |      |
|------|------|
| 名称 | DecimalToAnyBase |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/conversions/DecimalToAnyBase.java |
| 包名 | com.thealgorithms.conversions |
| 依赖项 | ['java.util.ArrayList', 'java.util.List'] |
| 概述说明 | 将十进制数转换为2至36进制字符串。 |

# 说明

该功能用于将十进制数转换为指定进制的字符串表示，支持的进制范围从2到36。通过输入一个十进制数和一个目标进制值，函数会将该数转换为相应进制的字符串形式。这一转换过程涵盖了从二进制到三十六进制的所有可能进制，确保了广泛的适用性和灵活性。该功能适用于需要在不同进制之间进行转换的场景，如计算机科学、数学计算和数据处理等领域。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| DecimalToAnyBase | class | 将十进制数转换为指定进制的字符串表示，支持2到36进制。 |



## 类 DecimalToAnyBase

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | DecimalToAnyBase |
| 说明 | 将十进制数转换为指定进制的字符串表示，支持2到36进制。 |


### UML类图

```mermaid
classDiagram
    class DecimalToAnyBase {
        -static final int MIN_BASE
        -static final int MAX_BASE
        -static final char ZERO_CHAR
        -static final char A_CHAR
        -static final int DIGIT_OFFSET
        +static String convertToAnyBase(int decimal, int base)
        -static char convertToChar(int value)
    }
```

这段代码定义了一个名为 `DecimalToAnyBase` 的类，该类包含两个静态方法：`convertToAnyBase` 和 `convertToChar`。`convertToAnyBase` 方法用于将十进制整数转换为指定基数的字符串表示，支持基数范围在2到36之间。`convertToChar` 方法用于将整数值转换为对应的字符表示，其中0-9对应字符 '0'-'9'，10-35对应字符 'A'-'Z'。该类通过私有构造函数确保不可实例化，所有方法均为静态方法，适用于工具类的设计模式。


### 内部方法调用关系图

```mermaid
graph TD
    A["类DecimalToAnyBase"]
    B["常量: MIN_BASE = 2"]
    C["常量: MAX_BASE = 36"]
    D["常量: ZERO_CHAR = '0'"]
    E["常量: A_CHAR = 'A'"]
    F["常量: DIGIT_OFFSET = 10"]
    G["私有构造方法: DecimalToAnyBase()"]
    H["静态方法: convertToAnyBase(int decimal, int base)"]
    I["私有静态方法: convertToChar(int value)"]
    J["检查base是否在范围内"]
    K["检查decimal是否为0"]
    L["创建List<Character> digits"]
    M["循环: decimal > 0"]
    N["调用convertToChar(decimal % base)"]
    O["将结果添加到digits"]
    P["decimal /= base"]
    Q["创建StringBuilder result"]
    R["循环: 从digits.size() - 1到0"]
    S["将digits.get(i)添加到result"]
    T["返回result.toString()"]
    U["检查value是否在0-9之间"]
    V["返回(ZERO_CHAR + value)"]
    W["返回(A_CHAR + value - DIGIT_OFFSET)"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    A --> H
    A --> I
    H --> J
    H --> K
    H --> L
    H --> M
    M --> N
    N --> O
    O --> P
    P --> M
    H --> Q
    H --> R
    R --> S
    S --> R
    H --> T
    I --> U
    U --> V
    U --> W
```

这段代码实现了一个将十进制数转换为任意进制字符串表示的功能。类`DecimalToAnyBase`包含两个主要方法：`convertToAnyBase`用于将十进制数转换为指定进制的字符串，`convertToChar`用于将数值转换为对应的字符。流程图展示了代码的执行流程，包括参数检查、循环处理、字符转换和结果构建等步骤。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| MIN_BASE = 2 | int | 定义常量MIN_BASE，值为2。 |
| MAX_BASE = 36 | int | 定义私有静态常量MAX_BASE，值为36。 |
| A_CHAR = 'A' | char | 定义私有静态常量字符A，值为'A'。 |
| DIGIT_OFFSET = 10 | int | 私有静态常量DIGIT_OFFSET值为10。 |
| ZERO_CHAR = '0' | char | 定义私有静态常量ZERO_CHAR，值为字符'0'。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| convertToChar | char | 将整数值转换为对应字符，0-9为数字，其他为字母。 |
| convertToAnyBase | String | 将十进制数转换为任意进制字符串，支持进制范围校验。 |




