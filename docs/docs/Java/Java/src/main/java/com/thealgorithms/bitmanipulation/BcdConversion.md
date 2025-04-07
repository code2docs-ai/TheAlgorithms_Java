# 基础信息

|      |      |
|------|------|
| 名称 | BcdConversion |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/bitmanipulation/BcdConversion.java |
| 包名 | com.thealgorithms.bitmanipulation |
| 依赖项 | [] |
| 概述说明 | BcdConversion类实现BCD与十进制互转，含校验和转换步骤。 |

# 说明

BcdConversion类提供了BCD码与十进制数之间的相互转换功能，包含了完整的校验和转换步骤，确保数据在转换过程中的准确性和完整性。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| BcdConversion | class | BcdConversion类实现BCD与十进制互转，包含校验和转换步骤。 |



## 类 BcdConversion

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | BcdConversion |
| 说明 | BcdConversion类实现BCD与十进制互转，包含校验和转换步骤。 |


### UML类图

```mermaid
classDiagram
    class BcdConversion {
        -BcdConversion()
        +int bcdToDecimal(int bcd)
        +int decimalToBcd(int decimal)
    }
```

这段代码定义了一个名为 `BcdConversion` 的类，该类包含两个静态方法：`bcdToDecimal` 和 `decimalToBcd`。`bcdToDecimal` 方法将二进制编码的十进制数（BCD）转换为十进制数，而 `decimalToBcd` 方法则将十进制数转换为BCD。这两个方法都包含输入验证，以确保输入的数值在有效范围内。`BcdConversion` 类的构造函数被私有化，防止实例化该类。类图展示了该类的结构和方法的访问权限。


### 内部方法调用关系图

```mermaid
graph TD
    A["类BcdConversion"]
    B["私有构造方法: BcdConversion()"]
    C["静态方法: int bcdToDecimal(int bcd)"]
    D["静态方法: int decimalToBcd(int decimal)"]
    E["初始化: int decimal = 0, int multiplier = 1"]
    F["循环: while (bcd > 0)"]
    G["提取BCD数字: int digit = bcd & 0xF"]
    H["验证BCD数字: if (digit > 9)"]
    I["抛出异常: throw new IllegalArgumentException('Invalid BCD digit: ' + digit)"]
    J["计算十进制数: decimal += digit * multiplier"]
    K["更新乘数: multiplier *= 10"]
    L["右移BCD数: bcd >>= 4"]
    M["返回结果: return decimal"]
    N["验证十进制数: if (decimal < 0 || decimal > 9999)"]
    O["抛出异常: throw new IllegalArgumentException('Value out of bounds for BCD representation: ' + decimal)"]
    P["初始化: int bcd = 0, int shift = 0"]
    Q["循环: while (decimal > 0)"]
    R["提取十进制数字: int digit = decimal % 10"]
    S["更新BCD数: bcd |= (digit << (shift * 4))"]
    T["移除十进制数字: decimal /= 10"]
    U["增加移位: shift++"]
    V["返回结果: return bcd"]

    A --> B
    A --> C
    A --> D
    C --> E
    C --> F
    F --> G
    G --> H
    H --> I
    H --> J
    J --> K
    K --> L
    L --> F
    F --> M
    D --> N
    N --> O
    N --> P
    P --> Q
    Q --> R
    R --> S
    S --> T
    T --> U
    U --> Q
    Q --> V
```

该流程图描述了`BcdConversion`类中的两个主要方法：`bcdToDecimal`和`decimalToBcd`。`bcdToDecimal`方法将BCD数转换为十进制数，首先验证BCD数字的有效性，然后逐位提取并计算十进制数。`decimalToBcd`方法将十进制数转换为BCD数，首先验证十进制数的范围，然后逐位提取并构建BCD数。两个方法都通过循环处理输入数字，并在过程中进行相应的位操作和计算。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| decimalToBcd | int | 将十进制数转换为BCD码，支持0到9999范围。 |
| bcdToDecimal | int | 将BCD码转换为十进制数，验证每位并计算。 |




