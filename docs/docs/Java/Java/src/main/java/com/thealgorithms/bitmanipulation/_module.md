# 基础信息

|      |      |
|------|------|
| 名称 | bitmanipulation |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/bitmanipulation |
| 包名 | Java.src.main.java.com.thealgorithms.bitmanipulation |
| 概述说明 | 检查两整数是否仅有一位不同，涉及逐位比较并统计不同位数。 |

# 说明

## 概述
该代码模块主要涉及位操作（Bit Manipulation）相关的算法和工具类，提供了丰富的功能来处理二进制数据、整数位操作、逻辑运算等。模块中的各个类和方法涵盖了从基本的位操作（如反转、交换、清除、设置比特位）到更复杂的算法（如汉明距离、格雷码转换、子集生成等）。这些功能广泛应用于算法优化、数据结构处理、加密算法、图像处理等领域，能够显著提升代码的性能和可读性。

## 主要业务场景
1. **位操作与二进制处理**：模块中的多个类和方法专注于处理整数的二进制表示，包括反转比特位、交换比特位、清除或设置特定比特位、查找最高或最低有效位等。这些操作在需要精细控制二进制数据的场景中非常有用，如加密算法、压缩算法、图像处理等。

2. **算法优化与数据处理**：模块提供了一些高效的算法，如通过位运算生成子集、计算汉明距离、查找非重复元素等。这些算法在优化数据处理、减少时间复杂度、提升性能方面具有重要作用，适用于大规模数据处理的场景。

3. **编码转换与逻辑运算**：模块包含了多种编码转换功能，如BCD码与十进制数的转换、二进制与格雷码的转换等。此外，还实现了基本的布尔代数门操作（如与门、或门、异或门等），这些功能在数字电路设计、信号处理等领域有广泛应用。

4. **数学运算与位运算结合**：模块中的一些方法结合了数学运算与位运算，如判断整数是否为2的幂次方、计算整数的补码、查找下一个更高或更低的2的幂次方等。这些功能在需要结合数学和位运算的场景中非常有用，如算法设计、数值计算等。

5. **特定问题的解决方案**：模块还提供了一些针对特定问题的解决方案，如查找数组中唯一出现奇数次的整数、判断两个整数是否仅有一位不同、计算整数的前导零个数等。这些功能在算法竞赛、面试题解答等场景中非常实用。


### 包内部结构视图

```mermaid
graph TD
    bitmanipulation --> OneBitDifference.java
    bitmanipulation --> LowestSetBit.java
    bitmanipulation --> NumberAppearingOddTimes.java
    bitmanipulation --> ReverseBits.java
    bitmanipulation --> BitSwap.java
    bitmanipulation --> ParityCheck.java
    bitmanipulation --> GenerateSubsets.java
    bitmanipulation --> CountSetBits.java
    bitmanipulation --> BooleanAlgebraGates.java
    bitmanipulation --> BinaryPalindromeCheck.java
    bitmanipulation --> ModuloPowerOfTwo.java
    bitmanipulation --> SingleBitOperations.java
    bitmanipulation --> FirstDifferentBit.java
    bitmanipulation --> HighestSetBit.java
    bitmanipulation --> OnesComplement.java
    bitmanipulation --> FindNthBit.java
    bitmanipulation --> HigherLowerPowerOfTwo.java
    bitmanipulation --> TwosComplement.java
    bitmanipulation --> IsEven.java
    bitmanipulation --> NonRepeatingNumberFinder.java
    bitmanipulation --> ClearLeftmostSetBit.java
    bitmanipulation --> Xs3Conversion.java
    bitmanipulation --> SwapAdjacentBits.java
    bitmanipulation --> SingleElement.java
    bitmanipulation --> NumbersDifferentSigns.java
    bitmanipulation --> BcdConversion.java
    bitmanipulation --> GrayCodeConversion.java
    bitmanipulation --> IndexOfRightMostSetBit.java
    bitmanipulation --> HammingDistance.java
    bitmanipulation --> NextHigherSameBitCount.java
    bitmanipulation --> CountLeadingZeros.java
    bitmanipulation --> IsPowerTwo.java
```

该流程图展示了`bitmanipulation`目录下的所有文件及其层级关系。每个文件都是`bitmanipulation`的直接子节点，表示这些文件都属于同一个目录。这些文件涵盖了多种位操作相关的算法和功能实现。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [IsEven.java](IsEven.md) | file | IsEven类包含静态方法isEven，用于判断整数是否为偶数。 |
| [OnesComplement.java](OnesComplement.md) | file | OnesComplement类用于计算二进制数的反码。 |
| [IsPowerTwo.java](IsPowerTwo.md) | file | 通过位运算快速判断整数是否为2的幂次方。 |
| [IndexOfRightMostSetBit.java](IndexOfRightMostSetBit.md) | file | 查找整数最右置位索引，返回零基索引，无置位返回-1。 |
| [SingleElement.java](SingleElement.md) | file | 单例类使用位运算XOR在O(n)时间内查找数组中的唯一非重复元素。 |
| [ModuloPowerOfTwo.java](ModuloPowerOfTwo.md) | file | 计算整数除以2的n次方的余数，n为正整数。 |
| [ParityCheck.java](ParityCheck.md) | file | ParityCheck类的checkParity方法检查整数奇偶性并返回布尔值。 |
| [NumberAppearingOddTimes.java](NumberAppearingOddTimes.md) | file | 查找数组中唯一出现奇数次的整数。 |
| [ClearLeftmostSetBit.java](ClearLeftmostSetBit.md) | file | 清除数字最左置位并返回结果。 |
| [CountLeadingZeros.java](CountLeadingZeros.md) | file | 统计二进制数前导零个数，右移掩码至最左位为1。 |
| [NextHigherSameBitCount.java](NextHigherSameBitCount.md) | file | 寻找比特数相同的下一个更大整数。 |
| [HammingDistance.java](HammingDistance.md) | file | 计算两整数汉明距离，返回不同位数数量。 |
| [GrayCodeConversion.java](GrayCodeConversion.md) | file | GrayCodeConversion类实现二进制与格雷码互转。 |
| [BcdConversion.java](BcdConversion.md) | file | BcdConversion类实现BCD与十进制互转，含校验和转换步骤。 |
| [NumbersDifferentSigns.java](NumbersDifferentSigns.md) | file | 通过位运算判断两整数符号是否相反。 |
| [SwapAdjacentBits.java](SwapAdjacentBits.md) | file | 交换整数相邻位，使用掩码和位移操作完成。 |
| [Xs3Conversion.java](Xs3Conversion.md) | file | XS-3与二进制互转工具类，提供双向转换方法。 |
| [NonRepeatingNumberFinder.java](NonRepeatingNumberFinder.md) | file | 通过异或运算查找数组中唯一不重复的数字。 |
| [TwosComplement.java](TwosComplement.md) | file | 计算二进制补码：取反后加一，处理进位，返回结果。 |
| [HigherLowerPowerOfTwo.java](HigherLowerPowerOfTwo.md) | file | 类HigherLowerPowerOfTwo提供查找高、低2的幂次方的方法。 |
| [FindNthBit.java](FindNthBit.md) | file | FindNthBit类提供静态方法findNthBit，用于获取整数指定位置位的值，位位置需≥1。 |
| [HighestSetBit.java](HighestSetBit.md) | file | 查找整数最高有效位索引，负数报错，0返回空。 |
| [FirstDifferentBit.java](FirstDifferentBit.md) | file | FirstDifferentBit类用异或操作确定两整数首个不同位的索引。 |
| [SingleBitOperations.java](SingleBitOperations.md) | file | 单比特操作类支持翻转、设置、清除和获取指定比特位功能。 |
| [BinaryPalindromeCheck.java](BinaryPalindromeCheck.md) | file | 检查二进制数是否为回文。 |
| [BooleanAlgebraGates.java](BooleanAlgebraGates.md) | file | 布尔代数门实现包含AND、OR、NOT、XOR、NAND和NOR门。 |
| [CountSetBits.java](CountSetBits.md) | file | Brian Kernighan算法高效计算二进制1的个数，查表法快速预处理0-255的1个数。 |
| [GenerateSubsets.java](GenerateSubsets.md) | file | 位运算生成集合所有子集。 |
| [BitSwap.java](BitSwap.md) | file | BitSwap类提供bitSwap方法，用于交换整数data中posA和posB位置的比特。 |
| [ReverseBits.java](ReverseBits.md) | file | ReverseBits类用于反转32位整数的二进制位。 |
| [LowestSetBit.java](LowestSetBit.md) | file | LowestSetBit类提供隔离和清除最低有效位的方法。 |
| [OneBitDifference.java](OneBitDifference.md) | file | 判断两整数是否仅有一位数字不同。 |


