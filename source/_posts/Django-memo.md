---
title: Django memo
date: 2024-03-28 15:53:41
tags:
---
2024-03-28
- python替换清华源 `pip3 config set global.index-url https://pypi.tuna.tsinghua.edu.cn/simple`
- 生成requirements.txt `pip3 freeze > ./requirements.txt`
- 安装requirements.txt `pip3 install -r requirements.txt`
- 新建app `python manage.py startapp app_name`
- 生成数据库迁移文件 `python manage.py makemigrations (app_name)`
- 执行数据库迁移 `python manage.py migrate (app_name)`（以上两个步骤可以根据model生成数据库表）
