# 基础信息

|      |      |
|------|------|
| 名称 | OctalToHexadecimal |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/conversions/OctalToHexadecimal.java |
| 包名 | com.thealgorithms.conversions |
| 依赖项 | [] |
| 概述说明 | 八进制转十进制，再转十六进制。 |

# 说明

该过程涉及将八进制字符串转换为十进制数值，再将十进制数值转换为十六进制表示。首先，八进制字符串通过基数8转换为十进制数值，然后该十进制数值通过基数16转换为十六进制字符串。整个转换过程确保了数值在不同进制之间的准确转换，最终得到十六进制结果。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| OctalToHexadecimal | class | 将八进制字符串转换为十进制，再将十进制转换为十六进制。 |



## 类 OctalToHexadecimal

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | OctalToHexadecimal |
| 说明 | 将八进制字符串转换为十进制，再将十进制转换为十六进制。 |


### UML类图

```mermaid
classDiagram
    class OctalToHexadecimal {
        -static final int OCTAL_BASE
        -static final int HEX_BASE
        -static final String HEX_DIGITS
        +OctalToHexadecimal()
        +static int octalToDecimal(String octalNumber)
        +static String decimalToHexadecimal(int decimalNumber)
    }
```

这段代码定义了一个名为 `OctalToHexadecimal` 的工具类，用于将八进制数转换为十六进制数。该类包含两个静态方法：`octalToDecimal` 和 `decimalToHexadecimal`。`octalToDecimal` 方法将八进制字符串转换为十进制整数，并处理无效输入的异常情况。`decimalToHexadecimal` 方法将十进制整数转换为十六进制字符串。该类通过私有构造函数防止实例化，确保其作为工具类的纯粹性。


### 内部方法调用关系图

```mermaid
graph TD
    A["类OctalToHexadecimal"]
    B["常量: int OCTAL_BASE = 8"]
    C["常量: int HEX_BASE = 16"]
    D["常量: String HEX_DIGITS = '0123456789ABCDEF'"]
    E["私有构造方法: OctalToHexadecimal()"]
    F["静态方法: int octalToDecimal(String octalNumber)"]
    G["静态方法: String decimalToHexadecimal(int decimalNumber)"]
    H["检查输入: if (octalNumber == null || octalNumber.isEmpty())"]
    I["抛出异常: throw new IllegalArgumentException('Input cannot be null or empty')"]
    J["初始化: int decimalValue = 0"]
    K["循环: for (int i = 0; i < octalNumber.length(); i++)"]
    L["获取字符: char currentChar = octalNumber.charAt(i)"]
    M["检查字符: if (currentChar < '0' || currentChar > '7')"]
    N["抛出异常: throw new IllegalArgumentException('Incorrect octal digit: ' + currentChar)"]
    O["计算: int currentDigit = currentChar - '0'"]
    P["更新: decimalValue = decimalValue * OCTAL_BASE + currentDigit"]
    Q["返回: return decimalValue"]
    R["检查输入: if (decimalNumber == 0)"]
    S["返回: return '0'"]
    T["初始化: StringBuilder hexValue = new StringBuilder()"]
    U["循环: while (decimalNumber > 0)"]
    V["计算: int digit = decimalNumber % HEX_BASE"]
    W["插入: hexValue.insert(0, HEX_DIGITS.charAt(digit))"]
    X["更新: decimalNumber /= HEX_BASE"]
    Y["返回: return hexValue.toString()"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    F --> H
    H --> I
    F --> J
    F --> K
    K --> L
    K --> M
    M --> N
    K --> O
    K --> P
    F --> Q
    G --> R
    R --> S
    G --> T
    G --> U
    U --> V
    U --> W
    U --> X
    G --> Y
```

这段代码定义了一个名为`OctalToHexadecimal`的类，包含两个静态方法：`octalToDecimal`和`decimalToHexadecimal`。`octalToDecimal`方法将八进制字符串转换为十进制整数，并处理无效输入。`decimalToHexadecimal`方法将十进制整数转换为十六进制字符串。代码通过循环和数学运算实现转换，并在每个步骤中检查输入的有效性，确保转换的准确性。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| HEX_BASE = 16 | int | 定义了一个私有的静态常量HEX_BASE，值为16。 |
| HEX_DIGITS = "0123456789ABCDEF" | String | 定义包含十六进制数字的常量字符串。 |
| OCTAL_BASE = 8 | int | 定义了一个静态常量OCTAL_BASE，其值为8，表示八进制基数。 |

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| decimalToHexadecimal | String | 将十进制数转换为十六进制字符串的Java方法。 |
| octalToDecimal | int | 将八进制字符串转换为十进制数，处理空值及非法字符。 |




