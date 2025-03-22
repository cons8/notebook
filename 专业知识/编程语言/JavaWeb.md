---
date: 2025-02-12
tags:
  - 编程
  - 后端
---
# JDBC
- 使用Java语言来操作关系型数据库
- 全称：Java DataBase Connectivity

## JDBC快速入门

```java
// 1.注册驱动  
Class.forName("com.mysql.cj.jdbc.Driver");  
// 2.获取连接  
String url = "jdbc:mysql://localhost:3306/db01";  
String username = "root";  
String password = "123456";  
Connection connection = DriverManager.getConnection(url, username, password);  
// 3.获取执行sql语句的对象  
Statement statement = connection.createStatement();  
// 4.执行sql语句  
String sql = "select * from user";  
ResultSet resultSet = statement.executeQuery(sql);  
// 5.处理结果  
while (resultSet.next()) {  
    int id = resultSet.getInt("id");  
    String name = resultSet.getString("username");  
    System.out.println(id + " " + name + " " + password );  
}  
// 6.释放资源  
resultSet.close();  
statement.close();
```

## JDBC API 详解

### DriverManager
驱动管理类：
1. 注册驱动
2. 获取数据库连接
### Connection
数据库连接对象：
- 获取执行SQL的对象
- 管理事务




# MyBatis
学习资料
[MyBatis中文网](https://mybatis.net.cn/index.html)






# JSP和Servlet
Servlet是运行在服务端的Java小程序，由sun公司提供的一套规范(接口)，用来处理客户端的请求，响应动态资源给浏览器
JSP本质是Servlet
实现步骤：
1. 创建类继承HttpServlet方法
2. 覆盖未实现的方法--service方法
## 1.1、JSP
Servlet的作用：用Java语言开发动态资源的技术
JSP的作用：用Java语言+html语言开发动态资源的技术

## 1.2 JSP的脚本
语法: `<%java代码%>`
作用：执行java代码

## 1.3 JSP表达式
语法： `<%=变量表达式%>`
作用：像浏览器输出变量的值或表达式计算的结果

# 转发、重定向
**转发（Forward）​** 和 ​**重定向（Redirect）​** 是Web开发中两种常见的请求处理机制，它们的核心区别在于**处理阶段**和**客户端行为**的不同：
**转发（Forward）​** 和 ​**重定向（Redirect）​** 是Web开发中两种常见的请求处理机制，它们的核心区别在于**处理阶段**和**客户端行为**的不同：

---

### 1. ​**转发（Forward）​**

- ​**服务器端内部跳转**  
    请求从客户端发到服务器后，服务器直接将请求转发给另一个内部资源（如JSP、Servlet、静态文件），​**客户端并不知情**。
- ​**URL不变**  
    浏览器地址栏仍显示原始请求的URL。
- ​**数据共享**  
    可以通过`HttpServletRequest`的属性传递数据（如参数、对象）。
- ​**示例场景**：  
    用户提交表单后，服务器验证成功，转发到结果页面，但URL保持不变。

---

### 2. ​**重定向（Redirect）​**

- ​**客户端发起新请求**  
    服务器返回一个HTTP状态码（如`301`或`302`）及新的URL，客户端浏览器根据该指令**重新发起请求**到新地址。
- ​**URL更新**  
    浏览器地址栏显示新的URL。
- ​**无法直接传递数据**  
    两次独立请求，需通过URL参数或会话（Session）传递数据。
- ​**示例场景**：  
    用户未登录时访问受保护页面，服务器重定向到登录页面；登录成功后跳转到原请求页面。
### 代码示例（Java Servlet）
#### 转发：


```java
request.getRequestDispatcher("/success.jsp").forward(request, response);
```

#### 重定向：


```java
response.sendRedirect("https://example.com/new-page");
```

# MVC
全名是Model View Controller，是模型 视图 控制器的缩写 一种软件设计典范
最简单，最经典的就是JSP（view）+Servlet（Controller）+JavaBean（model）
**视图和逻辑隔离开**
### **MVC 核心思想**
- ​**Model（模型）​**：负责数据处理和业务逻辑（如数据库操作、数据校验）。
- ​**View（视图）​**：负责数据显示（如 JSP、HTML 页面）。
- ​**Controller（控制器）​**：负责接收请求、调用模型处理数据，并选择合适的视图返回响应。
