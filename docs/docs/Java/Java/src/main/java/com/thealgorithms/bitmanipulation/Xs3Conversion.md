# 基础信息

|      |      |
|------|------|
| 名称 | Xs3Conversion |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/bitmanipulation/Xs3Conversion.java |
| 包名 | com.thealgorithms.bitmanipulation |
| 依赖项 | [] |
| 概述说明 | XS-3与二进制互转工具类，提供双向转换方法。 |

# 说明

XS-3与二进制互转工具类提供了两个核心方法：xs3ToBinary和binaryToXs3。xs3ToBinary方法用于将XS-3编码转换为二进制格式，而binaryToXs3方法则实现相反的功能，将二进制数据转换为XS-3编码。这两个方法共同构成了一个完整的工具类，便于在XS-3和二进制之间进行高效、准确的转换。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| Xs3Conversion | class | XS-3与二进制互转工具类，包含xs3ToBinary和binaryToXs3方法。 |



## 类 Xs3Conversion

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | Xs3Conversion |
| 说明 | XS-3与二进制互转工具类，包含xs3ToBinary和binaryToXs3方法。 |


### UML类图

```mermaid
classDiagram
    class Xs3Conversion {
        +Xs3Conversion()
        +static int xs3ToBinary(int xs3)
        +static int binaryToXs3(int binary)
    }
```

**描述：**
`Xs3Conversion` 类提供了两个静态方法，用于在 XS-3（Excess-3）编码和二进制数之间进行转换。`xs3ToBinary` 方法将 XS-3 编码的数字转换为二进制数，而 `binaryToXs3` 方法则将二进制数转换为 XS-3 编码。这两个方法通过位操作和算术运算实现了编码的转换，适用于需要处理 XS-3 编码的场景。


### 内部方法调用关系图

```mermaid
graph TD
    A["类Xs3Conversion"]
    B["私有构造方法: Xs3Conversion()"]
    C["静态方法: int xs3ToBinary(int xs3)"]
    D["静态方法: int binaryToXs3(int binary)"]
    E["初始化: int binary = 0, int multiplier = 1"]
    F["循环: while (xs3 > 0)"]
    G["提取并转换: int digit = (xs3 & 0xF) - 3"]
    H["累加: binary += digit * multiplier"]
    I["更新: multiplier *= 10, xs3 >>= 4"]
    J["返回: return binary"]
    K["初始化: int xs3 = 0, int shift = 0"]
    L["循环: while (binary > 0)"]
    M["提取并转换: int digit = (binary % 10) + 3"]
    N["移位累加: xs3 |= (digit << (shift * 4))"]
    O["更新: binary /= 10, shift++"]
    P["返回: return xs3"]

    A --> B
    A --> C
    A --> D
    C --> E
    C --> F
    F --> G
    F --> H
    F --> I
    C --> J
    D --> K
    D --> L
    L --> M
    L --> N
    L --> O
    D --> P
```

这段代码定义了一个名为`Xs3Conversion`的类，包含两个静态方法：`xs3ToBinary`和`binaryToXs3`。`xs3ToBinary`方法将XS-3（Excess-3）编码的数字转换为二进制数，通过逐位提取并减去3来实现。`binaryToXs3`方法则将二进制数转换为XS-3编码，通过逐位提取并加上3来实现。两个方法都通过循环处理每一位，并最终返回转换后的结果。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| xs3ToBinary | int | 将XS-3码转换为二进制数的Java方法。 |
| binaryToXs3 | int | 将二进制数转换为XS-3码，逐位加3并移位累加。 |




