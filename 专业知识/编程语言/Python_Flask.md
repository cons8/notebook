---
日期: 2025-02-26
tags:
  - 编程
  - 后端
  - Python
注释: 一个用 Python 编写的轻量级 Web 应用框架
---
> 参考教程  
> [Flask 教程 | 菜鸟教程](https://www.runoob.com/flask/flask-tutorial.html)
#  一、HelloFlask
## 1.1 Flask 特点
- **轻量级和简洁**：Flask 是一个微框架，提供了最基本的功能，不强制使用任何特定的工具或库。它的核心是简单而灵活的，允许开发者根据需要添加功能。
- **灵活性**：Flask 提供了基本的框架结构，但没有强制性的项目布局或组件，开发者可以根据自己的需求自定义。
- **可扩展性**：Flask 的设计允许你通过插件和扩展来添加功能。许多常见的功能，如表单处理、数据库交互和用户认证，都可以通过社区提供的扩展来实现。
- **内置开发服务器**：Flask 内置了一个开发服务器，方便在本地进行调试和测试。
- **RESTful 支持**：Flask 支持 RESTful API 的开发，适合构建现代的 Web 服务和应用程序。
## 1.2 安装
Flask 是 Python的一个库，所以首先需要确保你的计算机上已经安装了 Python。
Flask 需要 Python 3.6 及以上版本，先确保你已安装 Python 3。
### 1.2.1 使用 pip 安装 Flask
```shell
# 安装
pip install Flask
# 验证是否成功
pip show Flask
```
## 1.3 第一个Flask应用
首先，创建一个名为 app.py 的文件，并添加以下内容
```python
from flask import Flask

app = Flask(__name__)

@app.route('/')
def hello_world():
    return 'Hello, World!'

if __name__ == '__main__':
    app.run(debug=True)
```
在命令行中运行 Flask 应用：
```shell
python app.py
```
打开浏览器，访问 http://127.0.0.1:5000 应该会看到 "Hello, World!" 的消息，表示 Flask 已成功安装并运行。
