# 基础信息

|      |      |
|------|------|
| 名称 | maths |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/maths |
| 包名 | Java.src.main.java.com.thealgorithms.maths |
| 概述说明 | Means类计算算术、几何、调和均值，空输入抛出异常。 |

# 说明

## 概述
该代码模块是一个专注于数学计算和算法的Java库，涵盖了从基本的算术运算到复杂的数学问题求解的多种功能。模块中的每个类都专注于解决特定的数学问题，提供了高效的算法实现，确保了在各种应用场景中的准确性和性能。这些功能模块共同构成了一个强大的数学工具库，能够满足多种数学计算和算法应用的需求。

## 主要业务场景
1. **均值计算**：
   - **Means类**：用于计算算术均值、几何均值和调和均值，确保在输入有效的情况下能够准确计算三种不同类型的均值。如果输入数据为空，系统会检测并抛出异常，以防止无效计算或错误结果。

2. **快速幂运算**：
   - **FastExponentiation类**：用于高效计算大数的幂模运算，即计算 `(base^exp) % mod`。该算法通过将指数分解为二进制形式，减少乘法次数，从而提升计算效率，支持大数运算，确保在处理极大数值时仍能保持性能。

3. **长除法处理**：
   - **LongDivision类**：实现长除法时，处理整数除法的正负数和边界情况，确保长除法在各种情况下都能正确执行，包括除数为零时的异常处理和整数溢出的情况。

4. **数字属性验证**：
   - **FibonacciNumberCheck类**：提供方法用于判断数字是否为完全平方数或斐波那契数，帮助用户快速验证数字的数学特性。

5. **众数计算**：
   - **Mode类**：计算整数数组的众数，找出数组中出现次数最多的数，通过分析数组中的元素频率，确定并返回出现次数最多的那个数。

6. **字符串转整数**：
   - **ParseInteger类**：将字符串转换为整数，确保输入字符串的有效性和合法性，通过字符验证和转换逻辑，确保转换的准确性和鲁棒性。

7. **二次方程求解**：
   - **QuadraticEquationSolver类**：支持通过双参数和单参数构造复数，提供求解二次方程根的功能，确保能够处理所有可能的根情况，包括实根和虚根。

8. **素数查找**：
   - **SieveOfEratosthenes类**：使用埃拉托斯特尼筛法查找小于等于给定整数n的所有素数，通过逐步排除合数来确定素数，适用于大规模素数查找。

9. **数位和计算**：
   - **DigitalRoot类**：计算一个数字的数位和，直到结果变为单数，适用于需要快速确定数字根的场景。

10. **标准差计算**：
    - **StandardDeviation类**：计算数组的标准差，通过计算数据点与平均值的差的平方，求平均值的平方根，反映数据的波动情况。

11. **约瑟夫问题**：
    - **JosephusProblem类**：使用递归方法解决约瑟夫问题，通过将问题分解为更小的子问题，逐步推导出最终结果，适用于较大规模的参与者数量。

12. **亲和数查找**：
    - **AmicableNumber类**：查找指定范围内的亲和数对，并验证两个数是否构成亲和数，通过计算和比较数的真约数和，实现亲和数的识别与验证。

13. **最大公约数计算**：
    - **GCDRecursion类**：使用递归算法计算最大公约数，支持多组输入数据，确保每组的计算独立且准确。

14. **帕斯卡三角生成**：
    - **PascalTriangle类**：生成指定行数的帕斯卡三角数组，通过迭代或递归实现，确保每一行的数字准确无误，适用于需要帕斯卡三角数据的数学计算或图形展示场景。

15. **哥德巴赫猜想实现**：
    - **GoldbachConjecture类**：寻找两个质数，使得它们的和等于给定的偶数，实现哥德巴赫猜想，适用于需要验证哥德巴赫猜想的场景。

16. **快速傅里叶变换**：
    - **FFTBluestein类**：实现Bluestein的快速傅里叶变换算法，支持任意长度的序列，适用于需要高精度和灵活性的信号处理场景。

17. **矩阵行列式计算**：
    - **DeterminantOfMatrix类**：使用递归方法计算矩阵的行列式，适用于需要行列式计算的数学和工程应用，具备高效性和准确性。

18. **向量运算**：
    - **VectorCrossProduct类**：提供计算向量大小、点积和叉积的功能，支持向量的基本运算和展示，适用于需要进行向量计算的场景。

19. **Karatsuba乘法**：
    - **KaratsubaMultiplication类**：使用Karatsuba算法进行大数乘法，通过递归分治策略减少乘法次数，提升计算效率，适用于大规模数值计算。

20. **几何图形计算**：
    - **Perimeter类和Area类**：提供多种几何图形的周长和面积计算方法，确保输入参数为正数，适用于需要进行几何图形计算的场景。

这些功能模块共同构成了一个强大的数学工具库，能够满足多种数学计算和算法应用的需求。


### 包内部结构视图

```mermaid
graph TD
    maths --> Means.java
    maths --> FastExponentiation.java
    maths --> LongDivision.java
    maths --> FibonacciNumberCheck.java
    maths --> Mode.java
    maths --> ParseInteger.java
    maths --> QuadraticEquationSolver.java
    maths --> SieveOfEratosthenes.java
    maths --> DigitalRoot.java
    maths --> StandardDeviation.java
    maths --> Floor.java
    maths --> JosephusProblem.java
    maths --> Median.java
    maths --> TrinomialTriangle.java
    maths --> AmicableNumber.java
    maths --> SumOfDigits.java
    maths --> GCDRecursion.java
    maths --> SumWithoutArithmeticOperators.java
    maths --> PascalTriangle.java
    maths --> VampireNumber.java
    maths --> AbsoluteMax.java
    maths --> SumOfOddNumbers.java
    maths --> GenericRoot.java
    maths --> RomanNumeralUtil.java
    maths --> ChineseRemainderTheorem.java
    maths --> AutoCorrelation.java
    maths --> MathBuilder.java
    maths --> FindMax.java
    maths --> HeronsFormula.java
    maths --> AliquotSum.java
    maths --> FindMinRecursion.java
    maths --> HarshadNumber.java
    maths --> PollardRho.java
    maths --> CrossCorrelation.java
    maths --> SquareRootWithBabylonianMethod.java
    maths --> ReverseNumber.java
    maths --> SolovayStrassenPrimalityTest.java
    maths --> KeithNumber.java
    maths --> PiNilakantha.java
    maths --> FibonacciLoop.java
    maths --> GCD.java
    maths --> CollatzConjecture.java
    maths --> JugglerSequence.java
    maths --> FindMaxRecursion.java
    maths --> PowerUsingRecursion.java
    maths --> BinomialCoefficient.java
    maths --> LucasSeries.java
    maths --> ADTFraction.java
    maths --> StandardScore.java
    maths --> DudeneyNumber.java
    maths --> TwinPrime.java
    maths --> AutomorphicNumber.java
    maths --> SecondMinMax.java
    maths --> SumOfArithmeticSeries.java
    maths --> DistanceFormula.java
    maths --> UniformNumbers.java
    maths --> Prime
    Prime --> MillerRabinPrimalityCheck.java
    Prime --> PrimeFactorization.java
    Prime --> PrimeCheck.java
    Prime --> MobiusFunction.java
    Prime --> LiouvilleLambdaFunction.java
    Prime --> SquareFreeInteger.java
    maths --> PythagoreanTriple.java
    maths --> BinaryPow.java
    maths --> MaxValue.java
    maths --> NumberOfDigits.java
    maths --> Factorial.java
    maths --> MagicSquare.java
    maths --> FFTBluestein.java
    maths --> PronicNumber.java
    maths --> AbsoluteMin.java
    maths --> NonRepeatingElement.java
    maths --> Ceil.java
    maths --> FactorialRecursion.java
    maths --> FibonacciNumberGoldenRation.java
    maths --> Pow.java
    maths --> GoldbachConjecture.java
    maths --> SimpsonIntegration.java
    maths --> PerfectSquare.java
    maths --> Gaussian.java
    maths --> FrizzyNumber.java
    maths --> FFT.java
    maths --> Average.java
    maths --> LinearDiophantineEquationsSolver.java
    maths --> MinValue.java
    maths --> LeastCommonMultiple.java
    maths --> CatalanNumbers.java
    maths --> FindMin.java
    maths --> LeonardoNumber.java
    maths --> Convolution.java
    maths --> PowerOfTwoOrNot.java
    maths --> FibonacciJavaStreams.java
    maths --> NthUglyNumber.java
    maths --> PalindromeNumber.java
    maths --> DeterminantOfMatrix.java
    maths --> KrishnamurthyNumber.java
    maths --> FastInverseSqrt.java
    maths --> EulersFunction.java
    maths --> Volume.java
    maths --> PerfectNumber.java
    maths --> ConvolutionFFT.java
    maths --> CircularConvolutionFFT.java
    maths --> Armstrong.java
    maths --> KaprekarNumbers.java
    maths --> VectorCrossProduct.java
    maths --> KaratsubaMultiplication.java
    maths --> Perimeter.java
    maths --> FindKthNumber.java
    maths --> AbsoluteValue.java
    maths --> EulerMethod.java
    maths --> Combinations.java
    maths --> Area.java
    maths --> SquareRootWithNewtonRaphsonMethod.java
    maths --> StrobogrammaticNumber.java
    maths --> PerfectCube.java
```

该流程图展示了`maths`目录下的所有文件和子目录结构。`maths`作为根节点，直接连接了多个数学相关的Java文件，如`Means.java`、`FastExponentiation.java`等。此外，`Prime`作为子目录，进一步包含了多个与质数相关的文件，如`MillerRabinPrimalityCheck.java`和`PrimeFactorization.java`。整个流程图清晰地展示了文件之间的层级关系，便于理解项目结构。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [CrossCorrelation.java](CrossCorrelation.md) | file | CrossCorrelation类计算信号x和y的离散线性互相关，输出结果。 |
| [HarshadNumber.java](HarshadNumber.md) | file | HarshadNumber类用于判断数字是否为哈沙德数。 |
| [HeronsFormula.java](HeronsFormula.md) | file | HeronsFormula类验证边长并计算三角形面积。 |
| [RomanNumeralUtil.java](RomanNumeralUtil.md) | file | 罗马数字工具类，支持1到5999的数字转换。 |
| [VampireNumber.java](VampireNumber.md) | file | VampireNumber类用于判断两数是否为吸血鬼数，并可忽略伪吸血鬼数。 |
| [SumOfDigits.java](SumOfDigits.md) | file | SumOfDigits类提供三种计算数字各位之和的方法：循环、递归和字符数组法。 |
| [Floor.java](Floor.md) | file | Floor类方法返回最接近正无穷大的整数。 |
| [QuadraticEquationSolver.java](QuadraticEquationSolver.md) | file | 定义复数类，支持构造和二次方程根求解。 |
| [Mode.java](Mode.md) | file | 计算数组众数，返回频次最高数。 |
| [Means.java](Means.md) | file | Means类计算三种均值，输入为空时抛出异常。 |
| [MinValue.java](MinValue.md) | file | MinValue类的静态方法min返回两个整数中的较小值。 |
| [FFT.java](FFT.md) | file | 实现复数运算及快速傅里叶变换，支持正逆变换。 |
| [GoldbachConjecture.java](GoldbachConjecture.md) | file | GoldbachConjecture类用于查找两个质数之和等于指定偶数。 |
| [Ceil.java](Ceil.md) | file | Ceil类方法返回最接近负无穷的整数。 |
| [PronicNumber.java](PronicNumber.md) | file | PronicNumber类提供遍历和平方根优化两种方法判断Pronic数。 |
| [NumberOfDigits.java](NumberOfDigits.md) | file | NumberOfDigits类提供四种方法计算整数位数。 |
| [DistanceFormula.java](DistanceFormula.md) | file | DistanceFormula类支持欧几里得、曼哈顿、汉明和闵可夫斯基距离计算。 |
| [SecondMinMax.java](SecondMinMax.md) | file | SecondMinMax类用于查找数组中第二小或第二大值，数组长度需≥2且元素不全相同。 |
| [StandardScore.java](StandardScore.md) | file | StandardScore类提供静态方法计算Z分数。 |
| [FindMaxRecursion.java](FindMaxRecursion.md) | file | 递归分治法求数组最大值，支持指定范围。 |
| [FibonacciLoop.java](FibonacciLoop.md) | file | 计算第n个斐波那契数，采用循环方法，支持大整数计算。 |
| [StrobogrammaticNumber.java](StrobogrammaticNumber.md) | file | 验证数字对称性并检查字符映射关系。 |
| [Area.java](Area.md) | file | Area类支持多种几何图形面积计算，参数必须为正数，否则异常。 |
| [FindKthNumber.java](FindKthNumber.md) | file | FindKthNumber类提供快速选择和堆排序方法查找第k大元素。 |
| [KaprekarNumbers.java](KaprekarNumbers.md) | file | KaprekarNumbers类提供查找范围内Kaprekar数和判断某数是否为Kaprekar数的方法。 |
| [PerfectNumber.java](PerfectNumber.md) | file | 判断数字是否为完美数，需计算其所有正因子之和。 |
| [FastInverseSqrt.java](FastInverseSqrt.md) | file | FastInverseSqrt类提供两种方法计算逆平方根，精度6-8位和14-16位，时间复杂度O(1)。 |
| [FibonacciJavaStreams.java](FibonacciJavaStreams.md) | file | Java流式计算斐波那契数列，支持大数，返回Optional结果。 |
| [PerfectCube.java](PerfectCube.md) | file | PerfectCube类通过Math.pow和Math.cbrt函数检查数字是否为完全立方数。 |
| [SquareRootWithNewtonRaphsonMethod.java](SquareRootWithNewtonRaphsonMethod.md) | file | 使用牛顿迭代法计算整数平方根，精度达0.0000001。 |
| [Combinations.java](Combinations.md) | file | Combinations类提供阶乘、组合计算及优化，防止长整型溢出。 |
| [EulerMethod.java](EulerMethod.md) | file | EulerMethod类演示欧拉法解微分方程，含三例及结果输出。 |
| [AbsoluteValue.java](AbsoluteValue.md) | file | AbsoluteValue类提供整数绝对值获取方法。 |
| [Perimeter.java](Perimeter.md) | file | Perimeter类支持计算正多边形、不规则多边形、矩形和圆的周长。 |
| [KaratsubaMultiplication.java](KaratsubaMultiplication.md) | file | Karatsuba算法通过递归分治实现大数乘法。 |
| [VectorCrossProduct.java](VectorCrossProduct.md) | file | 向量叉积类：含构造函数，计算大小、点积、叉积，显示向量。 |
| [Armstrong.java](Armstrong.md) | file | 判断数字是否为阿姆斯壮数，返回布尔值。 |
| [CircularConvolutionFFT.java](CircularConvolutionFFT.md) | file | CircularConvolutionFFT类利用FFT和Bluestein算法实现快速循环卷积。 |
| [ConvolutionFFT.java](ConvolutionFFT.md) | file | 卷积FFT类利用零填充和FFT算法加速线性卷积计算。 |
| [Volume.java](Volume.md) | file | Volume类提供多种几何体体积计算的静态方法。 |
| [EulersFunction.java](EulersFunction.md) | file | 欧拉函数类，验证输入为正整数，时间复杂度为O(sqrt(n))。 |
| [KrishnamurthyNumber.java](KrishnamurthyNumber.md) | file | Krishnamurthy数指各位数字阶乘和等于该数本身的数。 |
| [DeterminantOfMatrix.java](DeterminantOfMatrix.md) | file | Java类实现矩阵行列式计算，采用递归方法。 |
| [PalindromeNumber.java](PalindromeNumber.md) | file | 判断整数是否为回文数，负数则抛出异常。 |
| [NthUglyNumber.java](NthUglyNumber.md) | file | NthUglyNumber类计算第n个丑数，支持初始化、获取及更新操作。 |
| [PowerOfTwoOrNot.java](PowerOfTwoOrNot.md) | file | 判断数字是否为2的幂。 |
| [Convolution.java](Convolution.md) | file | 卷积类实现离散线性卷积，输入信号从0开始并返回结果。 |
| [LeonardoNumber.java](LeonardoNumber.md) | file | LeonardoNumber类递归计算第n个Leonardo数列，起始值为1,1。 |
| [FindMin.java](FindMin.md) | file | FindMin类提供findMin方法，查找非空整数数组最小值，空数组抛出异常。 |
| [CatalanNumbers.java](CatalanNumbers.md) | file | 递归方法计算第n个卡塔兰数。 |
| [LeastCommonMultiple.java](LeastCommonMultiple.md) | file | 计算两个数的最小公倍数。 |
| [LinearDiophantineEquationsSolver.java](LinearDiophantineEquationsSolver.md) | file | Java实现线性丢番图方程求解，处理无解和无限解情况。 |
| [Average.java](Average.md) | file | Average类用于计算双精度和整数数组的平均值，且不可实例化。 |
| [FrizzyNumber.java](FrizzyNumber.md) | file | FrizzyNumber类的getNthFrizzy方法计算基数的第n个幂和。 |
| [Gaussian.java](Gaussian.md) | file | Gaussian类通过高斯消元法计算矩阵解并返回结果。 |
| [PerfectSquare.java](PerfectSquare.md) | file | PerfectSquare类提供两种方法验证数字是否为完全平方数。 |
| [SimpsonIntegration.java](SimpsonIntegration.md) | file | 辛普森法计算定积分，适用于偶数区间，通过公式评估积分值。 |
| [Pow.java](Pow.md) | file | Pow类计算a的b次方，b为非负整数，否则抛异常。 |
| [FibonacciNumberGoldenRation.java](FibonacciNumberGoldenRation.md) | file | Fibonacci类用黄金比例公式计算第n个数，输入上限为70以保证精度。 |
| [JugglerSequence.java](JugglerSequence.md) | file | JugglerSequence类根据奇偶性生成并打印从指定数开始的序列。 |
| [FactorialRecursion.java](FactorialRecursion.md) | file | 递归计算阶乘，处理负数异常。 |
| [NonRepeatingElement.java](NonRepeatingElement.md) | file | 类NonRepeatingElement的方法findNonRepeatingElements用于查找数组中两个不重复元素。 |
| [AbsoluteMin.java](AbsoluteMin.md) | file | 绝对最小值类用于比较数字并获取绝对值最小的值。 |
| [FFTBluestein.java](FFTBluestein.md) | file | FFTBluestein类实现Bluestein的FFT算法，支持正反变换。 |
| [MagicSquare.java](MagicSquare.md) | file | Java生成奇数阶魔方阵并打印输出。 |
| [Factorial.java](Factorial.md) | file | Java类通过迭代方法计算阶乘。 |
| [MaxValue.java](MaxValue.md) | file | MaxValue类的max方法返回两个int值中的较大者。 |
| [BinaryPow.java](BinaryPow.md) | file | BinaryPow类用于计算a的p次方，实现二进制幂运算。 |
| [PythagoreanTriple.java](PythagoreanTriple.md) | file | Java类验证三个数字是否满足勾股定理。 |
| [UniformNumbers.java](UniformNumbers.md) | file | UniformNumbers类计算1到num间均匀数，并统计a到b范围内的均匀数。 |
| [SumOfArithmeticSeries.java](SumOfArithmeticSeries.md) | file | SumOfArithmeticSeries类用于计算等差数列和，参数为首项、公差和项数。 |
| [AutomorphicNumber.java](AutomorphicNumber.md) | file | 类AutomorphicNumber提供判断数字是否为自守数的方法。 |
| [TwinPrime.java](TwinPrime.md) | file | TwinPrime类通过检查输入数及其加2是否为素数，返回加2或-1。 |
| [DudeneyNumber.java](DudeneyNumber.md) | file | DudeneyNumber类用于验证数字是否为立方等于其数字和的Dudeney数。 |
| [ADTFraction.java](ADTFraction.md) | file | 输入内容为空，无法生成概要描述。 |
| [LucasSeries.java](LucasSeries.md) | file | LucasSeries类提供递归和迭代方法计算Lucas数列第n项。 |
| [BinomialCoefficient.java](BinomialCoefficient.md) | file | 计算从n个对象中选取k个对象的组合数。 |
| [PowerUsingRecursion.java](PowerUsingRecursion.md) | file | 递归方法实现任意底数的整数次幂运算。 |
| [CollatzConjecture.java](CollatzConjecture.md) | file | CollatzConjecture类实现Collatz序列计算，包含nextNumber和collatzConjecture方法。 |
| [GCD.java](GCD.md) | file | GCD类提供计算最大公约数的方法。 |
| [PiNilakantha.java](PiNilakantha.md) | file | PiNilakantha类用无限级数计算Pi，迭代次数0到500。 |
| [KeithNumber.java](KeithNumber.md) | file | Java程序用于判断给定数字是否为Keith数。 |
| [SolovayStrassenPrimalityTest.java](SolovayStrassenPrimalityTest.md) | file | SolovayStrassen类实现素性测试，含模幂和雅可比符号计算，多次迭代提高准确性。 |
| [ReverseNumber.java](ReverseNumber.md) | file | ReverseNumber类提供静态方法reverseNumber，用于反转非负整数的数字顺序。 |
| [SquareRootWithBabylonianMethod.java](SquareRootWithBabylonianMethod.md) | file | Java类实现巴比伦方法计算平方根。 |
| [PollardRho.java](PollardRho.md) | file | PollardRho类包含g计算多项式模数和pollardRho寻找非平凡因子两个方法。 |
| [FindMinRecursion.java](FindMinRecursion.md) | file | 递归分治法实现数组最小值查找。 |
| [AliquotSum.java](AliquotSum.md) | file | AliquotSum类提供两个方法计算整数真约数和，分别采用流处理和优化计算效率。 |
| [FindMax.java](FindMax.md) | file | 工具类查找数组最大值，空数组抛出异常。 |
| [MathBuilder.java](MathBuilder.md) | file | MathBuilder类支持多种数学运算和函数。 |
| [AutoCorrelation.java](AutoCorrelation.md) | file | AutoCorrelation类计算离散信号自相关并返回结果。 |
| [ChineseRemainderTheorem.java](ChineseRemainderTheorem.md) | file | 中国剩余定理类，含求解方法与模逆计算。 |
| [GenericRoot.java](GenericRoot.md) | file | GenericRoot类递归求和数字各位数，直到结果为单数。 |
| [SumOfOddNumbers.java](SumOfOddNumbers.md) | file | SumOfOddNumbers类提供静态方法，计算前n个奇数和，返回n的平方。 |
| [AbsoluteMax.java](AbsoluteMax.md) | file | AbsoluteMax类用于获取数字绝对最大值，处理空或null输入异常。 |
| [PascalTriangle.java](PascalTriangle.md) | file | 帕斯卡三角类生成指定行数的帕斯卡三角数组。 |
| [SumWithoutArithmeticOperators.java](SumWithoutArithmeticOperators.md) | file | 递归方法无需算术运算符实现两数相加。 |
| [GCDRecursion.java](GCDRecursion.md) | file | Java递归计算最大公约数，支持多组输入并输出结果。 |
| [AmicableNumber.java](AmicableNumber.md) | file | AmicableNumber类用于查找和验证给定范围内的亲和数对。 |
| [TrinomialTriangle.java](TrinomialTriangle.md) | file | TrinomialTriangle类实现三项式三角形计算与打印。 |
| [Median.java](Median.md) | file | 计算排序数组的中位数，偶数取平均值，奇数取中间值。 |
| [JosephusProblem.java](JosephusProblem.md) | file | 约瑟夫问题通过递归计算确定游戏胜者。 |
| [StandardDeviation.java](StandardDeviation.md) | file | 计算数组标准差的静态方法。 |
| [DigitalRoot.java](DigitalRoot.md) | file | DigitalRoot类计算数字的数位和，直到结果为单数，时间复杂度O(位数^2)，空间复杂度O(位数)。 |
| [SieveOfEratosthenes.java](SieveOfEratosthenes.md) | file | 埃拉托斯特尼筛法用于找出小于等于n的所有素数。 |
| [ParseInteger.java](ParseInteger.md) | file | ParseInteger类实现字符串转整数，含输入检查、字符验证和转换逻辑。 |
| [FibonacciNumberCheck.java](FibonacciNumberCheck.md) | file | 该类提供两个静态方法：判断完全平方数和斐波那契数。 |
| [LongDivision.java](LongDivision.md) | file | 实现长除法，处理整数正负及边界情况。 |
| [FastExponentiation.java](FastExponentiation.md) | file | 快速幂算法实现大数幂模运算，具备完善异常处理。 |
| [Prime](Prime/_module.md) | package | MillerRabin算法提供概率和确定性素性检测，质因数分解类高效分解整数，质数验证结合常规和费马测试，Mobius和Liouville函数计算特定值，SquareFreeInteger检查无平方数。 |


