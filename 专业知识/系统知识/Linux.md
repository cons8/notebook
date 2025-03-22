---
date: 2025-02-20
注释: Linux一些操作的命令
tags:
  - Linux
  - 后端
---

# 修改主机名

**单次修改（重启后会恢复）**

`sudo hostnamectl set-hostname 新主机名称`

输入完成后，需要重新打开一个终端

**永久修改（重启后不恢复）**

1. `vim /etc/hostname`
2. 将文件的内容修改为`新主机名`保存并关闭
3. 执行`sudo systemctl restart network`
4. 重新打开终端

# 添加用户

`sudo useradd -m 用户名`

> 这里的`-m`表示在创建该用户的时候，同时创建该用户的家目录

`sudo passwd 用户名`

执行这个命令后，按照提示输入新密码即可。