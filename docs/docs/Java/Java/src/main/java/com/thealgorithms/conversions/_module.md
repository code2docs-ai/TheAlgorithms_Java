# 基础信息

|      |      |
|------|------|
| 名称 | conversions |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/conversions |
| 包名 | Java.src.main.java.com.thealgorithms.conversions |
| 概述说明 | 多种Java工具类实现数值、进制、单位、颜色等转换功能，支持异常处理和验证。 |

# 说明

## 概述
该代码模块是一个专注于各种数值和单位转换的工具集合，涵盖了从简单的进制转换到复杂的颜色模式、IP地址、温度单位、罗马数字、英文单词等多种类型的转换功能。模块中的每个类都专注于特定的转换任务，提供了高效、准确且健壮的转换方法，适用于计算机科学、数学计算、数据处理、网络编程等多个领域。

## 主要业务场景
1. **进制转换**：支持二进制、八进制、十进制、十六进制等不同进制之间的相互转换，适用于需要跨进制计算或数据处理的场景。例如，`AnyBaseToDecimal`、`OctalToBinary`、`DecimalToAnyBase`、`HexToOct`等类。
2. **IP地址转换**：实现IPv4与IPv6地址之间的相互转换，适用于网络协议兼容性和地址扩展性场景。例如，`IPv6Converter`、`IPConverter`类。
3. **单位转换**：支持温度、长度、重量等不同单位之间的转换，适用于科学计算和工程应用。例如，`UnitsConverter`、`UnitConversions`类。
4. **罗马数字转换**：实现罗马数字与整数之间的相互转换，适用于历史数据或特定格式的处理。例如，`RomanToInteger`、`IntegerToRoman`类。
5. **英文单词与数字转换**：支持将英文单词转换为数字，或将数字转换为英文单词，适用于财务报告、国际化文本处理等场景。例如，`WordsToNumber`、`NumberToWords`、`IntegerToEnglish`类。
6. **颜色模式转换**：实现RGB与HSV颜色模式之间的相互转换，适用于图像处理和设计领域。例如，`RgbHsvConversion`类。
7. **摩斯电码转换**：实现文本与摩斯电码之间的双向转换，适用于通信和编码场景。例如，`MorseCodeConverter`类。
8. **字符集转换**：支持土耳其字符与拉丁字符之间的转换，适用于多语言文本处理。例如，`TurkishToLatinConversion`类。
9. **仿射变换**：提供仿射变换的构造、转换、求逆和组合功能，适用于几何变换和图形处理场景。例如，`AffineConverter`类。

该模块通过提供多样化的转换工具，满足了不同应用场景下的需求，确保了转换过程的准确性、高效性和健壮性。


### 包内部结构视图

```mermaid
graph TD
    conversions --> AnyBaseToDecimal.java
    conversions --> OctalToBinary.java
    conversions --> OctalToDecimal.java
    conversions --> DecimalToAnyBase.java
    conversions --> PhoneticAlphabetConverter.java
    conversions --> UnitsConverter.java
    conversions --> IPv6Converter.java
    conversions --> RomanToInteger.java
    conversions --> BinaryToOctal.java
    conversions --> WordsToNumber.java
    conversions --> HexToOct.java
    conversions --> EndianConverter.java
    conversions --> HexaDecimalToDecimal.java
    conversions --> DecimalToHexadecimal.java
    conversions --> NumberToWords.java
    conversions --> AnyBaseToAnyBase.java
    conversions --> IntegerToRoman.java
    conversions --> UnitConversions.java
    conversions --> IPConverter.java
    conversions --> MorseCodeConverter.java
    conversions --> AnytoAny.java
    conversions --> HexaDecimalToBinary.java
    conversions --> BinaryToDecimal.java
    conversions --> TurkishToLatinConversion.java
    conversions --> RgbHsvConversion.java
    conversions --> BinaryToHexadecimal.java
    conversions --> DecimalToBinary.java
    conversions --> IntegerToEnglish.java
    conversions --> OctalToHexadecimal.java
    conversions --> AffineConverter.java
    conversions --> DecimalToOctal.java
```

该流程图展示了`conversions`目录下的所有文件层级关系。`conversions`作为根节点，直接连接到多个文件，这些文件涵盖了各种转换算法的实现，如进制转换、单位转换、编码转换等。每个文件都是独立的转换逻辑实现，没有进一步的子目录结构。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [RgbHsvConversion.java](RgbHsvConversion.md) | file | RGB与HSV颜色双向转换工具，附带测试用例。 |
| [MorseCodeConverter.java](MorseCodeConverter.md) | file | MorseCodeConverter类支持文本与摩斯码的双向转换。 |
| [IntegerToRoman.java](IntegerToRoman.md) | file | 整数转罗马数字工具类，通过数组映射和循环实现转换。 |
| [HexaDecimalToDecimal.java](HexaDecimalToDecimal.md) | file | 将十六进制字符串转为十进制整数，支持大小写，无效字符抛出异常。 |
| [WordsToNumber.java](WordsToNumber.md) | file | WordsToNumber类转换英文数字为数字，支持多种格式。WordsToNumberException处理错误信息。 |
| [UnitsConverter.java](UnitsConverter.md) | file | UnitsConverter类支持单位转换、逆转换、组合转换及单位列表查询。 |
| [OctalToDecimal.java](OctalToDecimal.md) | file | OctalToDecimal类将八进制转十进制，无效输入抛出异常。 |
| [DecimalToOctal.java](DecimalToOctal.md) | file | 将十进制数转换为八进制数的静态方法。 |
| [AffineConverter.java](AffineConverter.md) | file | AffineConverter类提供仿射变换功能，支持构造、转换、求逆和组合操作。 |
| [OctalToHexadecimal.java](OctalToHexadecimal.md) | file | 八进制转十进制，再转十六进制。 |
| [IntegerToEnglish.java](IntegerToEnglish.md) | file | Java工具类用于将整数转换为英文单词。 |
| [DecimalToBinary.java](DecimalToBinary.md) | file | DecimalToBinary类提供两种十进制转二进制方法：常规算法和位运算。 |
| [BinaryToHexadecimal.java](BinaryToHexadecimal.md) | file | 二进制转十六进制工具类，含映射初始化和转换方法，支持错误检测。 |
| [TurkishToLatinConversion.java](TurkishToLatinConversion.md) | file | 将土耳其字符转换为拉丁字符并返回结果。 |
| [BinaryToDecimal.java](BinaryToDecimal.md) | file | 将二进制数（仅含0和1）转换为十进制数。 |
| [HexaDecimalToBinary.java](HexaDecimalToBinary.md) | file | 将十六进制字符串转为至少8位二进制字符串。 |
| [AnytoAny.java](AnytoAny.md) | file | AnytoAny类支持2到10进制数字转换。 |
| [IPConverter.java](IPConverter.md) | file | IPConverter类实现IPv4地址与二进制互转。 |
| [UnitConversions.java](UnitConversions.md) | file | UnitConversions类实现多温度单位间转换功能。 |
| [AnyBaseToAnyBase.java](AnyBaseToAnyBase.md) | file | Java类实现2到36进制转换，验证输入并执行。 |
| [NumberToWords.java](NumberToWords.md) | file | Java类实现数字转英文单词，支持整数和小数转换。 |
| [DecimalToHexadecimal.java](DecimalToHexadecimal.md) | file | 将十进制数转十六进制字符串并去前导零。 |
| [EndianConverter.java](EndianConverter.md) | file | EndianConverter类实现32位整数大端小端互转。 |
| [HexToOct.java](HexToOct.md) | file | HexToOct类实现十六进制与十进制、八进制之间的转换功能。 |
| [BinaryToOctal.java](BinaryToOctal.md) | file | Java工具类实现二进制到八进制转换及验证功能。 |
| [RomanToInteger.java](RomanToInteger.md) | file | 罗马数字转整数工具类，支持字符验证与异常处理。 |
| [IPv6Converter.java](IPv6Converter.md) | file | IPv6Converter类提供IPv4与IPv6地址双向转换功能。 |
| [PhoneticAlphabetConverter.java](PhoneticAlphabetConverter.md) | file | PhoneticAlphabetConverter类实现文本转北约音标字母。 |
| [DecimalToAnyBase.java](DecimalToAnyBase.md) | file | 将十进制数转换为2至36进制字符串。 |
| [OctalToBinary.java](OctalToBinary.md) | file | 八进制数逐位转换为二进制数后拼接结果。 |
| [AnyBaseToDecimal.java](AnyBaseToDecimal.md) | file | AnyBaseToDecimal类实现任意进制字符串转十进制整数，支持数字和大写字母。 |


