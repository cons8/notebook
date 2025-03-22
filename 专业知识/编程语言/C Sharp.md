---
date: 2025-03-01
tags:
  - 编程
  - CSharp
  - Unity开发
---
# 一、C#是什么？

📌 C#是微软开发的"通用语言"，能用来：

- 🖥️ 开发Windows桌面软件（比如记事本替代品）
- 🎮 制作手机App（Xamarin框架）
- 🎮 开发游戏（Unity引擎必备）
- 💻 企业级后台系统
## 1.1 解决方案（Solution）
在 Visual Studio（或其他 IDE）中，解决方案（`.sln` 文件）是一个容器，用于管理一组相关联的 ​**项目（Project）​**。它描述了项目中各个文件的依赖关系和构建顺序。
**核心特性**：

1. ​**多项目聚合**​
    - 可以包含多个独立项目（如 Web API、Console App、Class Library）
    - 示例：一个电商系统可能包含 `OrderService`（微服务）、`AdminPortal`（管理后台）、`SharedLib`（公共组件）
2. ​**依赖管理**​
    - 通过 `Add Reference` 实现跨项目的代码复用
    - 自动处理项目间的编译顺序和依赖关系
3. ​**版本控制友好**​
    - 整个解决方案的源码可通过 Git 等工具集中管理
## 1.2 命名空间（Namespace）
命名空间（`namespace`）是 C# 中的一种逻辑代码组织机制，用于：
1. ​**避免命名冲突**​
    - 同一作用域内不允许重复的类型名，但不同命名空间可以包含同名类型
2. ​**实现代码分层**​
    - 将功能相关的类、接口、结构体组织到同一命名空间下

# 1.3 常见变量类型

### 一、值类型（Value Types）
**特点**：  
- 直接存储数据本身
- 在内存中占用固定大小
- 复制时复制实际值
#### 1. 基本数据类型
| 类型        | 描述        | 示例代码                       | 范围/大小            |
| --------- | --------- | -------------------------- | ---------------- |
| `int`     | 整数        | `int age = 25;`            | ±2^31-1          |
| `double`  | 浮点数       | `double price = 19.99;`    | 约±1.8e308        |
| `bool`    | 布尔值       | `bool isAvailable = true;` | true/false       |
| `char`    | Unicode字符 | `char c = 'A';`            | Unicode 0~U+FFFF |
| `decimal` | 高精度小数     | `decimal tax = 0.08m;`     | 28位精度            |

#### 2. 结构体（Struct）
**特点**：  
- 自定义复合数据类型（像「组装零件包」）
- 可以包含字段和方法

```csharp
// 定义结构体
public struct Point {
    public int X { get; set; }
    public int Y { get; set; }
}

// 使用示例
Point p = new Point { X = 10, Y = 20 };
```

#### 3. 枚举（Enum）
**特点**：  
- 表示固定集合的命名整数（像「扑克牌花色」）

```csharp
public enum Color {
    Red,
    Green,
    Blue
}

// 使用示例
Color favoriteColor = Color.Blue;
```

---

### 二、引用类型（Reference Types）📚
**特点**：  
- 存储对象的内存地址（像「商品目录书签」）
- 复制时复制引用而非实际数据
- 默认值为 `null`

#### 1. 对象（Object）
- 所有类型的基类
- 使用 `new` 关键字创建实例

```csharp
object obj = new object(); // 空对象
obj = "Hello World!"; // 多态特性
```
#### 2. 字符串（String）
- 不可变类型（修改会创建新对象）
- 特殊处理：直接使用引号声明
```csharp
string name = "张三";
name = name + "老师"; // 新字符串被创建
```
#### 3. 数组（Array）
- 固定长度的元素集合
- 声明语法：

```csharp
int[] scores = new int[5]; // 整型数组
string[] names = { "Alice", "Bob" }; // 初始化数组
```

#### 4. 动态类型（Dynamic）🔮
- 运行时确定类型（类似 JavaScript）
- 需在编译时开启 `dynamic` 关键字

```csharp
dynamic data = 123;       // 可以是数字
data = "Hello";         // 也可以是字符串
data.GetType();           // 运行时获取类型
```

---

### 三、值类型 vs 引用类型 
| 特性                | 值类型                   | 引用类型                   |
|---------------------|--------------------------|---------------------------|
| **内存分配**        | 栈（Stack）               | 堆（Heap）                 |
| **复制行为**        | 复制实际值               | 复制引用地址              |
| **默认值**          | 各类型不同（如 int=0）    | `null`                    |
| **速度**            | 更快                     | 较慢                      |

---

### 五、常见问题 ❓
1. **`int` 和 `Integer` 的区别？**  
   → `int` 是 C# 关键字，`Integer` 是 .NET Framework 中的别名，本质相同。

2. **为什么 `string` 是引用类型？**  
   → 为了实现字符串不可变性（保证内存安全和高效共享）。

3. **如何选择值类型/引用类型？**  
   → 小数据（如年龄、价格）用值类型，复杂对象（如用户信息）用引用类型。
