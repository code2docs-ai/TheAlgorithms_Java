# 基础信息

|      |      |
|------|------|
| 名称 | thealgorithms |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms |
| 包名 | Java.src.main.java.com.thealgorithms |
| 概述说明 | 代码模块实现了多种搜索算法、数据结构、加密算法、数学计算、动态规划等，适用于不同业务场景。 |

# 说明

## 概述

该代码模块是一个功能丰富的Java库，涵盖了从基础算法到复杂数据结构和数学计算的多种实现。模块中的各个子模块专注于不同的领域，包括搜索算法、矩阵操作、动态规划、贪心算法、图论、几何计算、加密算法、字符串处理、位操作、递归、分治算法、回溯算法、排序算法、进程调度、CRDT数据结构、音频滤波、滑动窗口、线段裁剪、数值转换等。这些实现通过高效的算法和清晰的设计，提供了广泛的功能，适用于多种业务场景和需求。

## 主要业务场景

1. **搜索算法**：模块提供了多种搜索算法，包括线性搜索、二分查找、图搜索、字符串匹配等，适用于有序数组、无序数组、二维数组、树、图等数据结构的查找任务。
2. **矩阵操作**：模块实现了矩阵的求逆、旋转、镜像、秩计算、转置、中位数计算、线性方程组求解等操作，适用于数学计算、数据处理、图像处理等领域。
3. **动态规划**：模块通过动态规划算法解决了子序列问题、路径计算、背包问题、字符串匹配等复杂问题，适用于需要优化和递归的场景。
4. **贪心算法**：模块实现了资源分配、调度问题、数学计算等贪心算法，适用于需要高效解决方案的场景。
5. **图论**：模块提供了带资源约束的最短路径、旅行商问题、强连通分量等图论问题的解决方案，适用于网络路由、物流配送、社交网络分析等场景。
6. **几何计算**：模块实现了凸包计算、直线生成、圆生成、椭圆生成等几何算法，适用于计算机图形学、计算几何等领域。
7. **加密算法**：模块涵盖了对称加密、非对称加密、流密码、替换密码、转置密码等多种加密技术，适用于数据加密、信息安全、通信保护等场景。
8. **字符串处理**：模块提供了字符串检查、转换、匹配、压缩、排列等多种功能，适用于文本处理、数据清洗、算法设计等领域。
9. **位操作**：模块实现了二进制数据处理、逻辑运算、编码转换等功能，适用于算法优化、数据结构处理、加密算法等领域。
10. **递归与分治算法**：模块通过递归和分治策略解决了棋盘填充、中位数查找、矩阵乘法、最近点对查找等问题，适用于大规模数据处理和复杂问题求解。
11. **回溯算法**：模块实现了组合、排列、路径搜索、图着色、迷宫求解、填字游戏等回溯算法，适用于需要穷举所有可能解的场景。
12. **排序算法**：模块涵盖了从经典排序算法到特殊排序算法的多种实现，适用于大规模数据排序、小规模数据排序、特定数据结构排序等场景。
13. **进程调度**：模块实现了多种进程调度算法，包括先来先服务、短作业优先、优先级调度、时间片轮转等，适用于操作系统、实时系统、云计算平台等场景。
14. **CRDT数据结构**：模块实现了无冲突复制数据类型，如集合、计数器等，适用于分布式系统中的高效数据管理和协同操作。
15. **音频滤波**：模块实现了IIR滤波器和EMAFilter，适用于音频信号的实时处理、噪声抑制、信号增强等场景。
16. **滑动窗口**：模块通过滑动窗口技术解决了子数组或子串相关的优化问题，适用于数据分析、时间序列处理、字符串处理等场景。
17. **线段裁剪**：模块实现了Cohen-Sutherland算法和Liang-Barsky算法，适用于二维平面几何图形的线段裁剪场景。
18. **数值转换**：模块提供了进制转换、IP地址转换、单位转换、罗马数字转换、颜色模式转换等功能，适用于计算机科学、数学计算、数据处理等领域。

这些业务场景展示了该模块的多样性和广泛适用性，能够满足从基础算法到复杂数据处理的多方面需求，提升开发效率和代码质量。


### 包内部结构视图

```mermaid
graph TD
    thealgorithms --> searches
    thealgorithms --> io
    thealgorithms --> audiofilters
    thealgorithms --> tree
    thealgorithms --> matrix
    thealgorithms --> datastructures
    thealgorithms --> bitmanipulation
    thealgorithms --> strings
    thealgorithms --> lineclipping
    thealgorithms --> slidingwindow
    thealgorithms --> puzzlesandgames
    thealgorithms --> recursion
    thealgorithms --> conversions
    thealgorithms --> others
    thealgorithms --> stacks
    thealgorithms --> misc
    thealgorithms --> backtracking
    thealgorithms --> dynamicprogramming
    thealgorithms --> graph
    thealgorithms --> divideandconquer
    thealgorithms --> geometry
    thealgorithms --> scheduling
    thealgorithms --> sorts
    thealgorithms --> greedyalgorithms
    thealgorithms --> maths
    thealgorithms --> ciphers
    thealgorithms --> devutils
    searches --> FibonacciSearch.java
    searches --> UpperBound.java
    searches --> JumpSearch.java
    searches --> DepthFirstSearch.java
    searches --> BreadthFirstSearch.java
    searches --> SortOrderAgnosticBinarySearch.java
    searches --> LowerBound.java
    searches --> BinarySearch2dArray.java
    searches --> UnionFind.java
    searches --> LinearSearch.java
    searches --> InterpolationSearch.java
    searches --> ExponentalSearch.java
    searches --> IterativeTernarySearch.java
    searches --> SearchInARowAndColWiseSortedMatrix.java
    searches --> IterativeBinarySearch.java
    searches --> RabinKarpAlgorithm.java
    searches --> BM25InvertedIndex.java
    searches --> HowManyTimesRotated.java
    searches --> MonteCarloTreeSearch.java
    searches --> QuickSelect.java
    searches --> RandomSearch.java
    searches --> TernarySearch.java
    searches --> SquareRootBinarySearch.java
    searches --> LinearSearchThread.java
    searches --> KMPSearch.java
    searches --> PerfectBinarySearch.java
    searches --> RowColumnWiseSorted2dArrayBinarySearch.java
    searches --> SaddlebackSearch.java
    searches --> RecursiveBinarySearch.java
    searches --> BinarySearch.java
    searches --> OrderAgnosticBinarySearch.java
    io --> BufferedReader.java
    audiofilters --> IIRFilter.java
    audiofilters --> EMAFilter.java
    tree --> HeavyLightDecomposition.java
    matrix --> InverseOfMatrix.java
    matrix --> RotateMatrixBy90Degrees.java
    matrix --> MirrorOfMatrix.java
    matrix --> MatrixRank.java
    matrix --> matrixexponentiation
    matrix --> PrintAMatrixInSpiralOrder.java
    matrix --> SolveSystem.java
    matrix --> utils
    matrix --> MedianOfMatrix.java
    matrix --> MatrixTranspose.java
    matrixexponentiation --> Fibonacci.java
    utils --> MatrixUtil.java
    datastructures --> crdt
    datastructures --> bloomfilter
    datastructures --> hashmap
    datastructures --> buffers
    datastructures --> stacks
    datastructures --> heaps
    datastructures --> trees
    datastructures --> lists
    datastructures --> disjointsetunion
    datastructures --> bags
    datastructures --> graphs
    datastructures --> dynamicarray
    datastructures --> queues
    datastructures --> caches
    crdt --> ORSet.java
    crdt --> PNCounter.java
    crdt --> GSet.java
    crdt --> TwoPSet.java
    crdt --> LWWElementSet.java
    crdt --> GCounter.java
    bloomfilter --> BloomFilter.java
    hashmap --> hashing
    hashing --> LinearProbingHashMap.java
    hashing --> Intersection.java
    hashing --> GenericHashMapUsingArray.java
    hashing --> MainCuckooHashing.java
    hashing --> HashMap.java
    hashing --> GenericHashMapUsingArrayList.java
    hashing --> Map.java
    hashing --> HashMapCuckooHashing.java
    hashing --> MajorityElement.java
    buffers --> CircularBuffer.java
    stacks --> Stack.java
    stacks --> StackOfLinkedList.java
    stacks --> ReverseStack.java
    stacks --> StackArrayList.java
    stacks --> NodeStack.java
    stacks --> StackArray.java
    heaps --> LeftistHeap.java
    heaps --> MinPriorityQueue.java
    heaps --> FibonacciHeap.java
    heaps --> MaxHeap.java
    heaps --> KthElementFinder.java
    heaps --> Heap.java
    heaps --> MedianFinder.java
    heaps --> HeapElement.java
    heaps --> MinHeap.java
    heaps --> MergeKSortedArrays.java
    heaps --> GenericHeap.java
    heaps --> EmptyHeapException.java
    trees --> BSTIterative.java
    trees --> CreateBinaryTreeFromInorderPreorder.java
    trees --> ZigzagTraversal.java
    trees --> AVLSimple.java
    trees --> KDTree.java
    trees --> CheckIfBinaryTreeBalanced.java
    trees --> AVLTree.java
    trees --> GenericTree.java
    trees --> PostOrderTraversal.java
    trees --> SplayTree.java
    trees --> InorderTraversal.java
    trees --> SameTreesCheck.java
    trees --> BSTRecursiveGeneric.java
    trees --> CheckBinaryTreeIsValidBST.java
    trees --> BSTFromSortedArray.java
    trees --> LCA.java
    trees --> PreOrderTraversal.java
    trees --> CeilInBinarySearchTree.java
    trees --> BinaryTree.java
    trees --> LevelOrderTraversal.java
    trees --> LazySegmentTree.java
    trees --> SegmentTree.java
    trees --> QuadTree.java
    trees --> Trie.java
    trees --> nearestRightKey.java
    trees --> PrintTopViewofTree.java
    trees --> Treap.java
    trees --> BSTRecursive.java
    trees --> TreeRandomNode.java
    trees --> RedBlackBST.java
    trees --> FenwickTree.java
    trees --> BoundaryTraversal.java
    trees --> VerticalOrderTraversal.java
    trees --> CheckTreeIsSymmetric.java
    lists --> RandomNode.java
    lists --> SkipList.java
    lists --> CursorLinkedList.java
    lists --> CircleLinkedList.java
    lists --> CountSinglyLinkedListRecursion.java
    lists --> SearchSinglyLinkedListRecursion.java
    lists --> RotateSinglyLinkedLists.java
    lists --> QuickSortLinkedList.java
    lists --> ReverseKGroup.java
    lists --> CreateAndDetectLoop.java
    lists --> MergeKSortedLinkedList.java
    lists --> SortedLinkedList.java
    lists --> DoublyLinkedList.java
    lists --> MergeSortedSinglyLinkedList.java
    lists --> SinglyLinkedList.java
    lists --> MergeSortedArrayList.java
    lists --> SinglyLinkedListNode.java
    disjointsetunion --> DisjointSetUnion.java
    disjointsetunion --> Node.java
    bags --> Bag.java
    graphs --> BellmanFord.java
    graphs --> MatrixGraphs.java
    graphs --> JohnsonsAlgorithm.java
    graphs --> UndirectedAdjacencyListGraph.java
    graphs --> TarjansAlgorithm.java
    graphs --> FordFulkerson.java
    graphs --> EdmondsBlossomAlgorithm.java
    graphs --> Kosaraju.java
    graphs --> WelshPowell.java
    graphs --> ConnectedComponent.java
    graphs --> AStar.java
    graphs --> BipartiteGraphDFS.java
    graphs --> PrimMST.java
    graphs --> BoruvkaAlgorithm.java
    graphs --> DijkstraOptimizedAlgorithm.java
    graphs --> FloydWarshall.java
    graphs --> KahnsAlgorithm.java
    graphs --> Graphs.java
    graphs --> Cycles.java
    graphs --> Kruskal.java
    graphs --> HamiltonianCycle.java
    graphs --> DijkstraAlgorithm.java
    dynamicarray --> DynamicArray.java
    queues --> SlidingWindowMaximum.java
    queues --> QueueByTwoStacks.java
    queues --> Queue.java
    queues --> GenericArrayListQueue.java
    queues --> TokenBucket.java
    queues --> LinkedQueue.java
    queues --> CircularQueue.java
    queues --> Deque.java
    queues --> PriorityQueues.java
    caches --> LFUCCache.java
    caches --> MRUCache.java
    caches --> LRUCCache.java
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
    strings --> Alphabetical.java
    strings --> CountChar.java
    strings --> Palindrome.java
    strings --> AhoCorasick.java
    strings --> Manacher.java
    strings --> Upper.java
    strings --> CheckAnagrams.java
    strings --> ReverseStringRecursive.java
    strings --> ValidParentheses.java
    strings --> CountWords.java
    strings --> HorspoolSearch.java
    strings --> Isomorphic.java
    strings --> Rotation.java
    strings --> LongestCommonPrefix.java
    strings --> CharactersSame.java
    strings --> StringMatchFiniteAutomata.java
    strings --> PermuteString.java
    strings --> CheckVowels.java
    strings --> LetterCombitionsOfPhoneNumber.java
    strings --> MyAtoi.java
    strings --> ReturnSubsequence.java
    strings --> RabinKarp.java
    strings --> KMP.java
    strings --> Anagrams.java
    strings --> WordLadder.java
    strings --> Pangram.java
    strings --> LongestNonRepetitiveSubstring.java
    strings --> Lower.java
    strings --> HammingDistance.java
    strings --> ReverseWordsInString.java
    strings --> LongestPalindromicSubstring.java
    strings --> ReverseString.java
    strings --> StringCompression.java
    strings --> zigZagPattern
    zigZagPattern --> ZigZagPattern.java
    lineclipping --> CohenSutherland.java
    lineclipping --> LiangBarsky.java
    lineclipping --> utils
    utils --> Point.java
    utils --> Line.java
    slidingwindow --> MinSumKSizeSubarray.java
    slidingwindow --> LongestSubarrayWithSumLessOrEqualToK.java
    slidingwindow --> MaxSumKSizeSubarray.java
    slidingwindow --> LongestSubstringWithoutRepeatingCharacters.java
    puzzlesandgames --> TowerOfHanoi.java
    puzzlesandgames --> WordBoggle.java
    puzzlesandgames --> Sudoku.java
    recursion --> GenerateSubsets.java
    recursion --> FibonacciSeries.java
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
    others --> MiniMaxAlgorithm.java
    others --> RemoveDuplicateFromString.java
    others --> ReverseStackUsingRecursion.java
    others --> BrianKernighanAlgorithm.java
    others --> Damm.java
    others --> Krishnamurthy.java
    others --> LineSweep.java
    others --> FloydTriangle.java
    others --> Mandelbrot.java
    others --> QueueUsingTwoStacks.java
    others --> GaussLegendre.java
    others --> LowestBasePalindrome.java
    others --> BFPRT.java
    others --> Huffman.java
    others --> InsertDeleteInArray.java
    others --> KochSnowflake.java
    others --> LinearCongruentialGenerator.java
    others --> Implementing_auto_completing_features_using_trie.java
    others --> Conway.java
    others --> ArrayRightRotation.java
    others --> CRCAlgorithm.java
    others --> ArrayLeftRotation.java
    others --> MaximumSlidingWindow.java
    others --> PageRank.java
    others --> PrintAMatrixInSpiralOrder.java
    others --> Verhoeff.java
    others --> Dijkstra.java
    others --> MemoryManagementAlgorithms.java
    others --> BankersAlgorithm.java
    others --> Luhn.java
    others --> PasswordGen.java
    others --> cn
    cn --> HammingDistance.java
    others --> TwoPointers.java
    others --> CRC16.java
    others --> HappyNumbersSeq.java
    others --> MaximumSumOfDistinctSubarraysWithLengthK.java
    others --> SkylineProblem.java
    others --> BoyerMoore.java
    others --> PerlinNoise.java
    others --> CRC32.java
    stacks --> SortStack.java
    stacks --> StackPostfixNotation.java
    stacks --> CelebrityFinder.java
    stacks --> NextSmallerElement.java
    stacks --> InfixToPostfix.java
    stacks --> SmallestElementConstantTime.java
    stacks --> MinStackUsingTwoStacks.java
    stacks --> LargestRectangle.java
    stacks --> StackUsingTwoQueues.java
    stacks --> PrefixEvaluator.java
    stacks --> InfixToPrefix.java
    stacks --> MinStackUsingSingleStack.java
    stacks --> GreatestElementConstantTime.java
    stacks --> PalindromeWithStack.java
    stacks --> DuplicateBrackets.java
    stacks --> BalancedBrackets.java
    stacks --> NextGreaterElement.java
    stacks --> MaximumMinimumWindow.java
    stacks --> PostfixEvaluator.java
    stacks --> PostfixToInfix.java
    stacks --> PrefixToInfix.java
    stacks --> DecimalToAnyUsingStack.java
    misc --> ColorContrastRatio.java
    misc --> MapReduce.java
    misc --> MedianOfRunningArrayInteger.java
    misc --> MedianOfRunningArray.java
    misc --> MedianOfRunningArrayFloat.java
    misc --> PalindromeSinglyLinkedList.java
    misc --> ShuffleArray.java
    misc --> MedianOfRunningArrayLong.java
    misc --> MedianOfRunningArrayDouble.java
    misc --> ThreeSumProblem.java
    misc --> Sparsity.java
    misc --> TwoSumProblem.java
    misc --> MedianOfRunningArrayByte.java
    misc --> PalindromePrime.java
    misc --> RangeInSortedArray.java
    backtracking --> ArrayCombination.java
    backtracking --> Permutation.java
    backtracking --> AllPathsFromSourceToTarget.java
    backtracking --> KnightsTour.java
    backtracking --> MazeRecursion.java
    backtracking --> FloodFill.java
    backtracking --> NQueens.java
    backtracking --> Combination.java
    backtracking --> PowerSum.java
    backtracking --> SubsequenceFinder.java
    backtracking --> ParenthesesGenerator.java
    backtracking --> WordPatternMatcher.java
    backtracking --> MColoring.java
    backtracking --> WordSearch.java
    backtracking --> CrosswordSolver.java
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
    dynamicprogramming --> Abbre

# 文件列表 File List

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| [audiofilters](audiofilters/_module.md) | package | IIR滤波器类实现无限脉冲响应滤波，支持系数设置和实时处理。EMAFilter类通过alpha参数实现指数移动平均滤波，适用于信号平滑处理。 |
| [searches](searches/_module.md) | package | 多种搜索算法实现，包括斐波那契、二分、跳转、深度优先、广度优先等，适用于不同场景。 |
| [devutils](devutils/_module.md) | package | 该模块包含搜索算法、进程管理和树节点管理的实现，适用于多种业务场景。 |
| [ciphers](ciphers/_module.md) | package | 多种加密算法类实现，涵盖AES、RSA、DES等，支持加密解密操作，确保数据安全性和完整性。 |
| [maths](maths/_module.md) | package | Means类计算算术、几何、调和均值，空输入抛出异常。 |
| [greedyalgorithms](greedyalgorithms/_module.md) | package | 贪心算法解决带宽分配、背包、找零、文件合并、股票利润、作业延迟、作业调度、二进制加法、埃及分数、区间合并、聚类中心、等待时间、活动选择、稳定婚姻、数字分离等问题。 |
| [sorts](sorts/_module.md) | package | 多种排序算法实现，包括基数、堆、选择、递归、Pancake、Circle、Comb、内省、二分插入、插入、Gnome、Stalin、自适应归并、Wiggle、Bead、快速、Patience、Spread、Dark、原地归并、Shell、桶、交换、Tree、拓扑、荷兰国旗、归并、Simple、Cycle、Flash、Pigeonhole、Wave、链表、冒泡、Slow、鸡尾酒、奇偶、计数、Swap、Bitonic、Bogo、Stooge、Tim、双轴快速排序等。 |
| [io](io/_module.md) | package | BufferedReader类支持单字节、块读取及预读功能。 |
| [scheduling](scheduling/_module.md) | package | 多种进程调度算法实现，优化系统资源利用和任务执行效率。 |
| [geometry](geometry/_module.md) | package | Graham Scan、MidpointCircle、Bresenham、ConvexHull、MidpointEllipse算法实现。 |
| [divideandconquer](divideandconquer/_module.md) | package | 递归分治策略解决棋盘填充、中位数查找、矩阵乘法、天空线生成、最近点对查找、逆序对统计及快速幂计算。 |
| [graph](graph/_module.md) | package | 动态规划解决资源约束最短路径；旅行商问题用暴力与动态规划；优化强连通分量算法用回溯与反向图。 |
| [dynamicprogramming](dynamicprogramming/_module.md) | package | 动态规划方法用于解决多种算法问题，包括子序列计数、路径计算、字符串匹配和优化问题。 |
| [backtracking](backtracking/_module.md) | package | 各类使用回溯法解决组合、排列、路径、迷宫、填充、N皇后、子序列、括号、模式匹配、图着色、单词搜索、填字游戏等问题。 |
| [misc](misc/_module.md) | package | 功能涵盖颜色对比度、单词频率统计、中位数计算、回文判断、数组打乱、矩阵稀疏度、两数和、三数和、质数判断等。 |
| [stacks](stacks/_module.md) | package | 各类栈算法实现，包括排序、表达式转换、名人查找、极值获取、回文检测等，均通过栈数据结构高效完成。 |
| [others](others/_module.md) | package | MiniMax算法递归计算最优得分，移除字符串重复字符，递归反转栈，高效计算置位数，Damm算法校验数据，判断Krishnamurthy数，范围最大值与重叠判断，生成Floyd三角形，Mandelbrot集图像生成，双栈实现队列，计算π值，最小回文基数，查找最小k元素，哈夫曼编码，数组插入删除，科赫雪花生成，伪随机数生成，Trie树实现，数数并说序列，数组右旋，CRC错误检测，数组左旋，滑动窗口最大值，PageRank网页排名，螺旋打印矩阵，Verhoeff校验和，Dijkstra最短路径，内存管理算法，银行家算法，Luhn信用卡验证，随机密码生成，汉明距离计算，双指针查找两数之和，CRC16校验，快乐数判断，最大和子数组，建筑物轮廓计算，多数元素查找，Perlin噪声生成，CRC32校验。 |
| [conversions](conversions/_module.md) | package | 多种Java工具类实现数值、进制、单位、颜色等转换功能，支持异常处理和验证。 |
| [recursion](recursion/_module.md) | package | GenerateSubsets递归生成字符串子集，FibonacciSeries递归计算斐波那契数列第n项。 |
| [puzzlesandgames](puzzlesandgames/_module.md) | package | 汉诺塔递归解法复杂度高，Boggle用Trie和DFS找词，数独回溯求解打印全。 |
| [slidingwindow](slidingwindow/_module.md) | package | 查找最小、最大和子数组及最长无重复子串的滑动窗口算法。 |
| [lineclipping](lineclipping/_module.md) | package | CohenSutherland和LiangBarsky算法用于线段裁剪，Point和Line类处理二维几何图形。 |
| [strings](strings/_module.md) | package | Java类实现多种字符串操作，包括字母顺序检查、字符统计、回文检测、模式匹配、子串查找、大小写转换、变位词验证、字符串反转、括号匹配、单词计数、同构检查、旋转操作、公共前缀查找、字符一致性验证、自动机匹配、排列生成、元音检查、电话键盘字母组合、字符串转整数、子序列生成、哈希匹配、KMP算法、变位词检测、单词转换、全字母句检测、最长不重复子串、小写转换、汉明距离计算、单词反转、回文子串查找、字符串压缩、Z形编码等。 |
| [bitmanipulation](bitmanipulation/_module.md) | package | 检查两整数是否仅有一位不同，涉及逐位比较并统计不同位数。 |
| [datastructures](datastructures/_module.md) | package | 代码模块实现多种数据结构，支持高效数据管理和协同操作，适用于高并发和分布式环境。 |
| [matrix](matrix/_module.md) | package | 矩阵操作类库，包含求逆、旋转、镜像、秩计算、斐波那契、螺旋打印、线性方程组求解、工具类、中位数计算和转置功能。 |
| [tree](tree/_module.md) | package | HeavyLightDecomposition类实现树分解，支持路径查询和更新。 |


