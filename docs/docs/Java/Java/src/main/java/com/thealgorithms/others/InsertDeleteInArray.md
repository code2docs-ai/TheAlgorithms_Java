# 基础信息

|      |      |
|------|------|
| 名称 | InsertDeleteInArray |
| 编码语言 | .java |
| 代码路径 | Java/src/main/java/com/thealgorithms/others/InsertDeleteInArray.java |
| 包名 | com.thealgorithms.others |
| 依赖项 | ['java.util.Scanner'] |
| 概述说明 | Java实现数组的插入与删除操作。 |

# 说明

Java程序实现数组插入和删除操作。数组插入操作涉及在指定位置插入新元素，需将后续元素后移以腾出空间。删除操作则需移除指定位置的元素，并将后续元素前移以填补空缺。这两种操作均需考虑数组长度和边界条件，确保操作合法且不引发异常。

# 类列表 Class Summary

| 名称   | 类型  | 说明 |
|-------|------|-------------|
| InsertDeleteInArray | class | Java程序实现数组插入和删除操作。 |



## 类 InsertDeleteInArray

|      |      |
|------|------|
| 访问范围 | public final |
| 类型 | class |
| 名称 | InsertDeleteInArray |
| 说明 | Java程序实现数组插入和删除操作。 |


### UML类图

```mermaid
classDiagram
    class InsertDeleteInArray {
        -InsertDeleteInArray()
        +main(String[] args)
    }
```

这段代码定义了一个名为 `InsertDeleteInArray` 的类，该类包含一个私有的构造函数和一个公有的 `main` 方法。`main` 方法负责处理用户输入，执行数组的插入和删除操作。首先，它读取数组的初始大小和元素，然后根据用户输入的索引和值插入新元素，最后根据用户输入的索引删除元素。整个过程通过控制台与用户交互，并输出操作后的数组内容。


### 内部方法调用关系图

```mermaid
graph TD
    A["类InsertDeleteInArray"]
    B["构造方法: InsertDeleteInArray()"]
    C["main方法: main(String[] args)"]
    D["创建Scanner对象: Scanner s = new Scanner(System.in)"]
    E["输出: 'Enter the size of the array'"]
    F["读取数组大小: int size = s.nextInt()"]
    G["创建数组: int[] a = new int[size]"]
    H["循环: for (i = 0; i < size; i++)"]
    I["输出: 'Enter the element'"]
    J["读取元素: a[i] = s.nextInt()"]
    K["输出: 'Enter the index at which the element should be inserted'"]
    L["读取插入位置: int insertPos = s.nextInt()"]
    M["输出: 'Enter the element to be inserted'"]
    N["读取插入元素: int ins = s.nextInt()"]
    O["创建新数组: int[] b = new int[size2]"]
    P["循环: for (i = 0; i < size2; i++)"]
    Q["判断: if (i <= insertPos)"]
    R["赋值: b[i] = a[i]"]
    S["赋值: b[i] = a[i - 1]"]
    T["插入元素: b[insertPos] = ins"]
    U["输出新数组元素: System.out.println(b[i])"]
    V["输出: 'Enter the index at which element is to be deleted'"]
    W["读取删除位置: int delPos = s.nextInt()"]
    X["循环: for (i = delPos; i < size2 - 1; i++)"]
    Y["删除元素: b[i] = b[i + 1]"]
    Z["输出删除后数组元素: System.out.println(b[i])"]

    A --> B
    A -.-> C
    C --> D
    D --> E
    E --> F
    F --> G
    G --> H
    H --> I
    I --> J
    H --> J
    C --> K
    K --> L
    L --> M
    M --> N
    N --> O
    O --> P
    P --> Q
    Q --> R
    Q --> S
    P --> T
    T --> U
    C --> V
    V --> W
    W --> X
    X --> Y
    Y --> Z
```

这段代码实现了一个简单的数组插入和删除操作。首先，用户输入数组的大小和初始元素。然后，用户可以选择在指定位置插入一个新元素，程序会创建一个新数组并将插入后的结果输出。接着，用户可以选择删除指定位置的元素，程序会调整数组并输出删除后的结果。整个过程通过循环和条件判断实现，确保数组的正确操作。

### 字段列表 Field List

| 名称  | 类型  | 说明 |
|-------|-------|------|

### 方法列表 Method List

| 名称  | 类型  | 说明 |
|-------|-------|------|
| main | void | Java程序：输入数组大小，初始化数组，插入元素，删除元素并输出结果。 |




