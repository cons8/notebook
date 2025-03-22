---
日期: 2025-02-26
tags:
  - 编程
  - Python
  - 软件测试
cssclasses:
  - Python自带的单元测试框架
最近更新: 2025-02-26T01:20:00
---
> 参考视频
> [十分钟极速入门Python unittest)

# 一、开始测试
## 1.1 啥是测试
**测试**就是**检查**你程序的运行结果是不是**你期待的结果**
换言之，在写测试的时候，你必须要知道正确答案，类似于批改卷子的过程。
## 1.2 怎么测试
首先测试文件也是一个python文件，并且这个文件要以  `test_`开头。
> 🔥 为什么文件要以`test_`开头？  
> → 这是Python测试框架的"暗号"，只有带这个前缀的方法才会被自动识别为测试用例
```python
# 1.首先我们要把unittest导入进来
import unittest
# 2.然后我们要把需要测试的内容导进来
from calculator import add, substract, multiply, divide
# 3.接下来是写test class，这个类首先必须要继承unittest里面的TestCase这个类
class calculatorTest(unittest.TestCase):
	# 一个testClass中可以多个测试方法，这些测试方法需要以 test_ 开头
	    def test_add(self):
	        self.assertEqual(add(1, 2), 3)
	        self.assertTrue(add(0, 0) == 0)

```
在项目根目录下运行 `python -m unittest` Python就会自动运行测试


>💡 费曼技巧：假设你是刚接触测试的新手，如何向同事解释为什么要使用`assertEqual`而不是直接用`assertTrue`？
> _使用具体断言可以：
> 1. 提供更清晰的错误信息 
> 2. 体现对业务逻辑的理解 
> 3. 方便后期维护"_ 


# 二、常见问题解决方案
## 2.1 测试找不到怎么办
```bash
# 检查三点：
1️⃣ 文件名必须以`test_`开头
2️⃣ 测试类必须继承TestCase
3️⃣ 方法必须以`test_`开头
```

