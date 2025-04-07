# 基础信息

|      |      |
|------|------|
| 名称 | dynamicprogramming |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/dynamicprogramming |
| 包名 | Java.src.main.java.com.thealgorithms.dynamicprogramming |
| 概述说明 | 动态规划方法用于解决多种算法问题，包括子序列计数、路径计算、字符串匹配和优化问题。 |

# 说明

## 概述

该代码模块主要聚焦于动态规划算法的实现与应用，涵盖了多种经典算法问题和优化策略。动态规划作为一种高效的算法设计技术，通过将复杂问题分解为子问题，并存储子问题的解来避免重复计算，从而显著提高算法的效率。该模块中的各个类和方法分别针对不同的业务场景，提供了多种解决方案，包括路径计算、子序列问题、背包问题、字符串匹配、矩阵链乘法等。这些实现不仅展示了动态规划的核心思想，还通过不同的优化策略（如记忆化、迭代、空间优化等）来提升算法的性能。

## 主要业务场景

1. **子序列与子串问题**：
   - **最长公共子序列**：计算两个字符串的最长公共子序列。
   - **最长递增子序列**：查找序列中最长的递增子序列。
   - **最长回文子序列/子串**：计算字符串中的最长回文子序列或子串。
   - **最长有效括号子串**：查找字符串中最长的有效括号子串。
   - **最长交替子序列**：计算序列中最长的交替增大或减小的子序列。
   - **最长等差子序列**：查找数组中最长的等差子序列。

2. **路径与组合问题**：
   - **网格路径计算**：计算从网格起点到终点的唯一路径数或最小路径和。
   - **爬楼梯问题**：计算爬n阶楼梯的不同方法数。
   - **矩阵链乘法**：计算矩阵乘法的最优顺序以最小化计算成本。
   - **骰子求和**：计算n个m面骰子得到和为x的方法数。

3. **背包与资源分配问题**：
   - **0-1背包问题**：计算在给定背包容量下能够获得的最大价值。
   - **最小分区和差**：计算将数组分为两个子集时的最小和差。
   - **硬币找零**：计算给定金额的硬币组合数或最小硬币数。
   - **最大子数组和**：查找数组中和最大的子数组。

4. **字符串匹配与编辑距离**：
   - **编辑距离**：计算将一个字符串转换为另一个字符串所需的最少操作次数。
   - **通配符匹配**：判断字符串是否与包含通配符的模式匹配。
   - **正则表达式匹配**：支持使用'?'和'*'通配符的字符串匹配。
   - **字符串缩写匹配**：判断字符串a是否可以通过转换和删除操作转换为字符串b。

5. **递归与优化问题**：
   - **递归动态规划**：通过递归和记忆化技术优化动态规划问题，如矩阵链乘法。
   - **任务分配**：使用位掩码技术计算任务分配方式的数量。
   - **树的最大加权匹配**：通过递归和动态规划计算树的最大加权匹配。
   - **最优作业调度**：计算多进程在多机器上的最优调度成本。

6. **其他经典问题**：
   - **鸡蛋掉落问题**：计算在给定鸡蛋和楼层情况下的最小试验次数。
   - **卡特兰数**：计算第n个卡特兰数。
   - **钢条切割**：计算钢条的最优切割方案以最大化价值。
   - **葡萄酒销售利润**：计算葡萄酒销售的最大利润。

这些业务场景涵盖了算法设计中的多个经典问题，展示了动态规划在不同领域的广泛应用。通过该模块的实现，用户可以高效地解决各种复杂的优化问题，并在实际应用中验证算法的正确性和性能。


### 包内部结构视图

```mermaid
graph TD
    dynamicprogramming --> UniqueSubsequencesCount.java
    dynamicprogramming --> CountFriendsPairing.java
    dynamicprogramming --> BoardPath.java
    dynamicprogramming --> EditDistance.java
    dynamicprogramming --> KadaneAlgorithm.java
    dynamicprogramming --> CoinChange.java
    dynamicprogramming --> SumOfSubset.java
    dynamicprogramming --> MatrixChainMultiplication.java
    dynamicprogramming --> Tribonacci.java
    dynamicprogramming --> Fibonacci.java
    dynamicprogramming --> LongestAlternatingSubsequence.java
    dynamicprogramming --> EggDropping.java
    dynamicprogramming --> PalindromicPartitioning.java
    dynamicprogramming --> LongestArithmeticSubsequence.java
    dynamicprogramming --> SubsetSum.java
    dynamicprogramming --> RegexMatching.java
    dynamicprogramming --> WineProblem.java
    dynamicprogramming --> LevenshteinDistance.java
    dynamicprogramming --> UniquePaths.java
    dynamicprogramming --> BoundaryFill.java
    dynamicprogramming --> LongestValidParentheses.java
    dynamicprogramming --> NewManShanksPrime.java
    dynamicprogramming --> LongestCommonSubsequence.java
    dynamicprogramming --> WildcardMatching.java
    dynamicprogramming --> MatrixChainRecursiveTopDownMemoisation.java
    dynamicprogramming --> MaximumSumOfNonAdjacentElements.java
    dynamicprogramming --> AssignmentUsingBitmask.java
    dynamicprogramming --> ShortestCommonSupersequenceLength.java
    dynamicprogramming --> PartitionProblem.java
    dynamicprogramming --> SubsetCount.java
    dynamicprogramming --> LongestPalindromicSubsequence.java
    dynamicprogramming --> KnapsackMemoization.java
    dynamicprogramming --> MinimumPathSum.java
    dynamicprogramming --> BruteForceKnapsack.java
    dynamicprogramming --> TreeMatching.java
    dynamicprogramming --> OptimalJobScheduling.java
    dynamicprogramming --> DiceThrow.java
    dynamicprogramming --> Knapsack.java
    dynamicprogramming --> MinimumSumPartition.java
    dynamicprogramming --> ClimbingStairs.java
    dynamicprogramming --> Abbreviation.java
    dynamicprogramming --> AllConstruct.java
    dynamicprogramming --> CatalanNumber.java
    dynamicprogramming --> SubsetSumSpaceOptimized.java
    dynamicprogramming --> RodCutting.java
    dynamicprogramming --> LongestPalindromicSubstring.java
    dynamicprogramming --> LongestIncreasingSubsequence.java
```

该流程图展示了`dynamicprogramming`目录下的所有Java文件及其层级关系。每个文件都直接隶属于`dynamicprogramming`目录，没有进一步的子目录嵌套。这些文件涵盖了多种动态编程算法的实现，如最长公共子序列、背包问题、编辑距离等。

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [CatalanNumber.java](CatalanNumber.md) | file | 使用动态规划计算第n个卡特兰数，n最大为50。 |
| [MinimumSumPartition.java](MinimumSumPartition.md) | file | MinimumSumPartition类通过动态规划计算数组最小分区和差，要求输入无负数。 |
| [TreeMatching.java](TreeMatching.md) | file | TreeMatching类递归计算树的最大加权匹配，DP表存储节点匹配结果。 |
| [MinimumPathSum.java](MinimumPathSum.md) | file | 计算二维网格左上到右下的最小路径和。 |
| [AssignmentUsingBitmask.java](AssignmentUsingBitmask.md) | file | 使用位掩码计算任务分配方式数。 |
| [MatrixChainRecursiveTopDownMemoisation.java](MatrixChainRecursiveTopDownMemoisation.md) | file | 递归动态规划求解矩阵链乘法最小标量乘法次数。 |
| [NewManShanksPrime.java](NewManShanksPrime.md) | file | 计算并验证第n个New Man Shanks素数是否符合预期值。 |
| [BoundaryFill.java](BoundaryFill.md) | file | BoundaryFill类实现图像像素颜色获取、设置及边界填充功能。 |
| [SubsetSum.java](SubsetSum.md) | file | SubsetSum类用于检查数组中是否存在子集，其元素之和等于指定值。 |
| [EggDropping.java](EggDropping.md) | file | EggDropping类用动态规划计算n蛋m楼最小试验次数。 |
| [Tribonacci.java](Tribonacci.md) | file | Tribonacci类通过迭代方法计算第n个Tribonacci数。 |
| [CoinChange.java](CoinChange.md) | file | CoinChange类提供计算硬币组合数和最小硬币数的方法。 |
| [CountFriendsPairing.java](CountFriendsPairing.md) | file | 计算并验证朋友配对序列结果。 |
| [SubsetCount.java](SubsetCount.md) | file | 动态规划解决子集和计数，时间复杂度O(n*target)，空间复杂度O(n*target)或O(target)。 |
| [LongestIncreasingSubsequence.java](LongestIncreasingSubsequence.md) | file | 该代码实现最长递增子序列算法，时间复杂度为O(nlogn)。 |
| [LongestPalindromicSubstring.java](LongestPalindromicSubstring.md) | file | 动态规划用于寻找字符串中的最长回文子串。 |
| [RodCutting.java](RodCutting.md) | file | 计算钢条切割方案，最大化n长度钢条的总价值。 |
| [SubsetSumSpaceOptimized.java](SubsetSumSpaceOptimized.md) | file | 一维布尔数组优化空间，检查子集是否含目标和。时间O(n*sum)，空间O(sum)。 |
| [AllConstruct.java](AllConstruct.md) | file | 查找构造目标字符串的所有方法，时间复杂度O(n*m*k)，空间复杂度O(n*m)。 |
| [Abbreviation.java](Abbreviation.md) | file | Abbreviation类用动态规划判断a能否通过大写和删除操作转为b。 |
| [ClimbingStairs.java](ClimbingStairs.md) | file | 动态规划实现计算爬n阶楼梯的不同方法数。 |
| [Knapsack.java](Knapsack.md) | file | Knapsack类用动态规划解决0-1背包问题，验证输入并计算最大价值。 |
| [DiceThrow.java](DiceThrow.md) | file | 动态规划计算n个m面骰子得到和为x的方案数。 |
| [OptimalJobScheduling.java](OptimalJobScheduling.md) | file | OptimalJobScheduling类计算多进程在多机器上的最优调度成本。 |
| [BruteForceKnapsack.java](BruteForceKnapsack.md) | file | BruteForceKnapsack类递归暴力求解0-1背包问题，返回最大价值。 |
| [KnapsackMemoization.java](KnapsackMemoization.md) | file | 动态规划优化背包问题，递归求最大利润，记忆化提升效率。 |
| [LongestPalindromicSubsequence.java](LongestPalindromicSubsequence.md) | file | Java类递归计算字符串最长回文子序列。 |
| [PartitionProblem.java](PartitionProblem.md) | file | PartitionProblem类用于判断整数数组能否分成两个和相等的子集。 |
| [ShortestCommonSupersequenceLength.java](ShortestCommonSupersequenceLength.md) | file | 计算两字符串最短超序列长度，基于最长公共子序列。 |
| [MaximumSumOfNonAdjacentElements.java](MaximumSumOfNonAdjacentElements.md) | file | 动态规划求解非相邻元素最大和，使用数组存储或变量优化两种方法。 |
| [WildcardMatching.java](WildcardMatching.md) | file | 动态规划实现通配符匹配算法。 |
| [LongestCommonSubsequence.java](LongestCommonSubsequence.md) | file | 计算两字符串的最长公共子序列。 |
| [LongestValidParentheses.java](LongestValidParentheses.md) | file | 计算字符串中最长有效括号子串的长度。 |
| [UniquePaths.java](UniquePaths.md) | file | UniquePaths类提供两种动态规划方法计算网格路径数，1D数组空间低，2D数组直观但空间高。 |
| [LevenshteinDistance.java](LevenshteinDistance.md) | file | Levenshtein距离类，含朴素和优化动态规划实现，计算字符串编辑距离，时间复杂度O(nm)，空间复杂度O(nm)和O(n)。 |
| [WineProblem.java](WineProblem.md) | file | 三种方法计算葡萄酒销售最大利润：递归、自上而下动态规划、自下而上动态规划。 |
| [RegexMatching.java](RegexMatching.md) | file | RegexMatching类提供四种方法匹配字符串与模式，支持'?'和'*'通配符。 |
| [LongestArithmeticSubsequence.java](LongestArithmeticSubsequence.md) | file | 计算数组中最长等差子序列的长度。 |
| [PalindromicPartitioning.java](PalindromicPartitioning.md) | file | 计算字符串回文分割的最小切割次数。 |
| [LongestAlternatingSubsequence.java](LongestAlternatingSubsequence.md) | file | 动态规划求解最长交替子序列长度。 |
| [Fibonacci.java](Fibonacci.md) | file | Fibonacci类提供四种计算第n个斐波那契数的方法。 |
| [MatrixChainMultiplication.java](MatrixChainMultiplication.md) | file | 矩阵链乘法类使用动态规划计算最优乘法顺序，返回最小成本和分割点。 |
| [SumOfSubset.java](SumOfSubset.md) | file | 递归检查数组子集和是否等于目标值。 |
| [KadaneAlgorithm.java](KadaneAlgorithm.md) | file | Kadane算法验证最大子数组和是否符合预期。 |
| [EditDistance.java](EditDistance.md) | file | 计算字符串编辑距离，支持插入、删除和替换操作。 |
| [BoardPath.java](BoardPath.md) | file | BoardPath类提供三种路径计算方法：无缓存递归、有缓存递归、迭代表驱动。 |
| [UniqueSubsequencesCount.java](UniqueSubsequencesCount.md) | file | UniqueSubsequencesCount类利用动态规划递归计算字符串唯一子序列数。 |


