# 基础信息

|      |      |
|------|------|
| 名称 | MillerRabinPrimalityCheck |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/maths/Prime/MillerRabinPrimalityCheck.java |
| 包名 | com.thealgorithms.maths.Prime |
| 依赖项 | ['java.util.Random'] |
| 概述说明 | MillerRabin算法用于素性检测，支持概率和确定性版本。 |

# 说明

MillerRabin算法用于素性检测，提供概率和确定性两种版本。概率版本通过多次迭代提高检测准确性，允许用户指定错误概率。确定性版本在特定范围内确保100%准确性，适用于需要绝对可靠性的场景。两种版本均基于数学理论，适用于大数检测，广泛应用于密码学等领域。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| MillerRabinPrimalityCheck | class | MillerRabin算法实现素性检测，包含概率和确定性版本。 |



## 类 MillerRabinPrimalityCheck

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | MillerRabinPrimalityCheck |
| 说明 | MillerRabin算法实现素性检测，包含概率和确定性版本。 |


### UML类图

```mermaid
classDiagram
    class MillerRabinPrimalityCheck {
        -MillerRabinPrimalityCheck()
        +boolean millerRabin(long n, int k)
        +boolean deterministicMillerRabin(long n)
        -boolean checkComposite(long n, long a, long d, int s)
        -long powerModP(long x, long y, long p)
        -long multiplyModP(long a, long b, long p)
    }
```

```mermaid
flowchart TD
    A["开始"] --> B["n < 4?"]
    B -- 是 --> C["n == 2 或 n == 3?"]
    C -- 是 --> D["返回 true"]
    C -- 否 --> E["返回 false"]
    B -- 否 --> F["计算 s 和 d"]
    F --> G["生成随机数 a"]
    G --> H["调用 checkComposite(n, a, d, s)"]
    H -- true --> I["返回 false"]
    H -- false --> J["继续迭代"]
    J -- 完成迭代 --> K["返回 true"]
```

```mermaid
sequenceDiagram
    participant A as 调用者
    participant B as MillerRabinPrimalityCheck
    A ->> B: millerRabin(n, k)
    B ->> B: 检查 n < 4
    alt n < 4
        B ->> B: 检查 n == 2 或 n == 3
        alt n == 2 或 n == 3
            B ->> A: 返回 true
        else
            B ->> A: 返回 false
        end
    else
        B ->> B: 计算 s 和 d
        loop k 次
            B ->> B: 生成随机数 a
            B ->> B: 调用 checkComposite(n, a, d, s)
            alt checkComposite 返回 true
                B ->> A: 返回 false
            end
        end
        B ->> A: 返回 true
    end
```

**描述**：`MillerRabinPrimalityCheck` 类实现了 Miller-Rabin 素性测试算法，用于判断一个数是否为素数。该算法分为概率性测试和确定性测试两种。概率性测试通过多次迭代来提高结果的准确性，而确定性测试则使用固定的素数基来确保结果的确定性。类中的私有方法 `checkComposite`、`powerModP` 和 `multiplyModP` 用于辅助计算和验证。


### 内部方法调用关系图

```mermaid
graph TD
    A["类MillerRabinPrimalityCheck"]
    B["构造方法: MillerRabinPrimalityCheck()"]
    C["方法: boolean millerRabin(long n, int k)"]
    D["方法: boolean deterministicMillerRabin(long n)"]
    E["方法: boolean checkComposite(long n, long a, long d, int s)"]
    F["方法: long powerModP(long x, long y, long p)"]
    G["方法: long multiplyModP(long a, long b, long p)"]
    H["条件: n < 4"]
    I["返回: n == 2 || n == 3"]
    J["初始化: int s = 0, long d = n - 1"]
    K["循环: (d & 1) == 0"]
    L["更新: d >>= 1, s++"]
    M["初始化: Random rnd = new Random()"]
    N["循环: i = 0 to k"]
    O["生成: long a = 2 + rnd.nextLong(n) % (n - 3)"]
    P["调用: checkComposite(n, a, d, s)"]
    Q["返回: false"]
    R["返回: true"]
    S["条件: n < 2"]
    T["返回: false"]
    U["初始化: int r = 0, long d = n - 1"]
    V["循环: (d & 1) == 0"]
    W["更新: d >>= 1, r++"]
    X["循环: a in [2, 3, 5, 7, 11, 13, 17, 19, 23, 29, 31, 37]"]
    Y["条件: n == a"]
    Z["返回: true"]
    AA["调用: checkComposite(n, a, d, r)"]
    AB["返回: false"]
    AC["返回: true"]
    AD["调用: powerModP(a, d, n)"]
    AE["条件: x == 1 || x == n - 1"]
    AF["返回: false"]
    AG["循环: r = 1 to s"]
    AH["调用: powerModP(x, 2, n)"]
    AI["条件: x == n - 1"]
    AJ["返回: false"]
    AK["返回: true"]
    AL["初始化: long res = 1"]
    AM["更新: x = x % p"]
    AN["条件: x == 0"]
    AO["返回: 0"]
    AP["循环: y > 0"]
    AQ["条件: (y & 1) == 1"]
    AR["调用: multiplyModP(res, x, p)"]
    AS["更新: y = y >> 1, x = multiplyModP(x, x, p)"]
    AT["返回: res"]
    AU["计算: long aHi = a >> 24, long aLo = a & ((1 << 24) - 1)"]
    AV["计算: long bHi = b >> 24, long bLo = b & ((1 << 24) - 1)"]
    AW["计算: long result = ((((aHi * bHi << 16) % p) << 16) % p) << 16"]
    AX["更新: result += ((aLo * bHi + aHi * bLo) << 24) + aLo * bLo"]
    AY["返回: result % p"]

    A --> B
    A --> C
    A --> D
    A --> E
    A --> F
    A --> G
    C --> H
    H --> I
    H --> J
    J --> K
    K --> L
    K --> M
    M --> N
    N --> O
    O --> P
    P --> Q
    P --> R
    D --> S
    S --> T
    S --> U
    U --> V
    V --> W
    V --> X
    X --> Y
    Y --> Z
    X --> AA
    AA --> AB
    X --> AC
    E --> AD
    AD --> AE
    AE --> AF
    AD --> AG
    AG --> AH
    AH --> AI
    AI --> AJ
    AG --> AK
    F --> AL
    AL --> AM
    AM --> AN
    AN --> AO
    AN --> AP
    AP --> AQ
    AQ --> AR
    AP --> AS
    AP --> AT
    G --> AU
    AU --> AV
    AV --> AW
    AW --> AX
    AX --> AY
```

这段代码实现了Miller-Rabin素性测试算法，包括概率性和确定性两种版本。概率性版本通过多次随机测试判断一个数是否为素数，而确定性版本则通过固定的一组基数进行测试。代码中还包含了用于辅助计算的模幂运算和模乘运算方法。整个流程通过逐步分解和验证，确保算法的正确性和效率。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| millerRabin | boolean | 米勒-拉宾素数测试，判断n是否为素数，通过k次随机测试提高准确性。 |
| powerModP | long | 计算x的y次方模p，通过逐次平方和乘法优化性能。 |
| checkComposite | boolean | 检查合数方法：通过幂模运算验证n是否为合数。 |
| multiplyModP | long | 该方法通过分解和重组长整型数实现模乘运算。 |
| deterministicMillerRabin | boolean | 确定性的Miller-Rabin算法，用于判断整数n是否为素数。 |




