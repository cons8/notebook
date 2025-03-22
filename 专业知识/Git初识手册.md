---
date: 2025-02-24
tags:
  - git
  - 编程
  - 学习方法
---
# 一、为什么需要git？
## 1.1 之前我是怎么保存文件的
想象你在写毕业论文时：
- 删除了整章内容却找不到备份
- 和室友合作时覆盖彼此的修改
- 不同电脑上的文档版本混乱
## 1.2 Git的魔法
它能像「时光机管理员」一样：  
✅ 记录所有修改历史（精确到每行代码）  
✅ 支持多人协作而不冲突  
✅ 快速回滚到任意版本

# 二、初次见面多多指教
## 2.1 Git的核心概念
**仓库（Repository）**
- 每个项目一个独立仓库（类似手机相册的不同相册夹）
**提交（Commit）**
- 记录修改人+时间+内容说明（就像给照片贴标签）
**分支（Branch）**
- 同时进行多个任务的「平行世界」  
- 完成一个任务后合并回主分支（类似电影拍摄的A/B组镜头）
**远程仓库（Remote）**
- 云端备份箱（如Google Drive但更专业）  
- 团队共享协作的基础
## 2.2 你好，这是我的名片
下载好 Git 后，通常需要进行以下一些基本操作：
- **设置用户名和邮箱**：在命令行中输入以下命令来设置你的用户名和邮箱，这将用于标识你在版本控制系统中的身份，在提交代码时会记录这些信息。
```shell
git config --global user.name "Your Name"
git config --global user.email "your_email@example.com"
```
- **检查配置**：可以通过以下命令检查配置是否正确。
```shell
git config --list
```
# 三、上手实操！
## 3.1 创建或克隆仓库
- **创建新的本地仓库**：如果你有一个新的项目需要进行版本控制，在项目目录下打开命令行，执行以下命令将当前目录初始化为 Git 仓库。
```shell
# 创建git仓库
git init
```
- **克隆远程仓库**：如果你想从远程服务器获取一个已有的项目仓库到本地，可以使用`git clone`命令，后面跟上远程仓库的 URL。例如：
```shell
git clone https://github.com/example/repo.git
```
## 3.2 记录修改
```shell
# 将文件添加到「待提交区」
git add README.md

# 提交更改（附上本次修改说明）
git commit -m "完成项目介绍文档"
```

## 3.3 查看历史
```shell
# 展示提交时间线
git log --oneline

# 回退到指定版本
git checkout commit_id
```


---
# 学习资源扩展
[Git教程 - 廖雪峰的官方网站](https://liaoxuefeng.com/books/git/introduction/index.html)