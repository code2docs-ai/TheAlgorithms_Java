# 基础信息

|      |      |
|------|------|
| 名称 | BinaryToHexadecimal |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/conversions/BinaryToHexadecimal.java |
| 包名 | com.thealgorithms.conversions |
| 依赖项 | ['java.util.HashMap', 'java.util.Map'] |
| 概述说明 | 二进制转十六进制工具类，含映射初始化和转换方法，支持错误检测。 |

# 说明

该工具类专注于二进制到十六进制的转换，提供了初始化映射和转换方法。初始化映射用于建立二进制与十六进制之间的对应关系，确保转换过程的准确性和高效性。转换方法实现了从二进制到十六进制的实际转换，支持对输入数据的错误检测，确保输入格式的正确性。该工具类设计简洁，功能明确，适用于需要二进制与十六进制互转的场景。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| BinaryToHexadecimal | class | 二进制转十六进制工具类，包含初始化映射和转换方法，支持错误检测。 |



## 类 BinaryToHexadecimal

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | BinaryToHexadecimal |
| 说明 | 二进制转十六进制工具类，包含初始化映射和转换方法，支持错误检测。 |


### UML类图

```mermaid
classDiagram
    class BinaryToHexadecimal {
        -static final int BITS_IN_HEX_DIGIT
        -static final int BASE_BINARY
        -static final int BASE_DECIMAL
        -static final int HEX_START_DECIMAL
        -static final int HEX_END_DECIMAL
        -BinaryToHexadecimal()
        +static String binToHex(int binary)
        -static Map~Integer, String~ initializeHexMap()
    }
```

**描述：**  
`BinaryToHexadecimal` 类是一个工具类，用于将二进制数转换为十六进制数。它包含一个私有的构造函数，确保无法实例化该类。`binToHex` 方法接受一个整数形式的二进制数，并将其转换为十六进制字符串。如果输入包含非二进制数字（即非0或1），则抛出 `IllegalArgumentException` 异常。`initializeHexMap` 方法初始化一个映射表，将十进制数字映射到对应的十六进制字符。该类通过静态方法和常量实现功能，确保了代码的简洁性和可重用性。


### 内部方法调用关系图

```mermaid
graph TD
    A["类BinaryToHexadecimal"]
    B["常量: int BITS_IN_HEX_DIGIT = 4"]
    C["常量: int BASE_BINARY = 2"]
    D["常量: int BASE_DECIMAL = 10"]
    E["常量: int HEX_START_DECIMAL = 10"]
    F["常量: int HEX_END_DECIMAL = 15"]
    G["构造方法: BinaryToHexadecimal()"]
    H["方法: String binToHex(int binary)"]
    I["方法: Map<Integer, String> initializeHexMap()"]
    J["变量: Map<Integer, String> hexMap = initializeHexMap()"]
    K["变量: StringBuilder hex = new StringBuilder()"]
    L["循环: while (binary != 0)"]
    M["变量: int decimalValue = 0"]
    N["循环: for (int i = 0; i < BITS_IN_HEX_DIGIT; i++)"]
    O["变量: int currentBit = binary % BASE_DECIMAL"]
    P["条件: if (currentBit > 1)"]
    Q["抛出异常: IllegalArgumentException"]
    R["操作: binary /= BASE_DECIMAL"]
    S["操作: decimalValue += (int) (currentBit * Math.pow(BASE_BINARY, i))"]
    T["操作: hex.insert(0, hexMap.get(decimalValue))"]
    U["返回: return !hex.isEmpty() ? hex.toString() : '0'"]
    V["初始化: Map<Integer, String> hexMap = new HashMap<>()"]
    W["循环: for (int i = 0; i < BASE_DECIMAL; i++)"]
    X["操作: hexMap.put(i, String.valueOf(i))"]
    Y["循环: for (int i = HEX_START_DECIMAL; i <= HEX_END_DECIMAL; i++)"]
    Z["操作: hexMap.put(i, String.valueOf((char) ('A' + i - HEX_START_DECIMAL)))"]
    AA["返回: return hexMap"]

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
    L --> M
    L --> N
    N --> O
    N --> P
    P --> Q
    N --> R
    N --> S
    L --> T
    H --> U
    I --> V
    I --> W
    W --> X
    I --> Y
    Y --> Z
    I --> AA
```

这段代码定义了一个`BinaryToHexadecimal`类，用于将二进制数转换为十六进制数。代码首先初始化了一个包含十进制到十六进制映射的哈希表，然后通过循环将二进制数逐位转换为十进制，再从哈希表中查找对应的十六进制字符，最终拼接成完整的十六进制字符串。如果输入的二进制数包含非0或1的字符，则会抛出异常。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| BASE_DECIMAL = 10 | int | 定义私有静态常量BASE_DECIMAL，值为10。 |
| HEX_END_DECIMAL = 15 | int | 定义了一个私有静态常量HEX_END_DECIMAL，值为15。 |
| BASE_BINARY = 2 | int | 定义私有静态常量BASE_BINARY，值为2。 |
| BITS_IN_HEX_DIGIT = 4 | int | 私有静态常量，表示十六进制数字的位数为4。 |
| HEX_START_DECIMAL = 10 | int | 定义私有静态常量HEX_START_DECIMAL，值为10。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| binToHex | String | 将二进制数转换为十六进制字符串的函数。 |
| initializeHexMap | Map<Integer, String> | 初始化十六进制映射表，包含数字和字母。 |




