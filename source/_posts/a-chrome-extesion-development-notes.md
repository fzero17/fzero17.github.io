---
title: 开发了一个 Chrome 浏览器插件
date: 2024-11-08 11:10:00
tags:
---

## 插件功能说明

功能点：

- 使用 GitHub 作为笔记本，不用担心笔记丢失。
- 使用 GitHub Pages 展示笔记，可以随时随地查看。

## 开发笔记

### 使用 Jekyll 向 GitHub Pages 站点添加主题

根据[说明文档](https://docs.github.com/en/pages/setting-up-a-github-pages-site-with-jekyll/adding-a-theme-to-your-github-pages-site-using-jekyll)，在根目录添加一个`_config.yml`文件，然后在里面添加主题就可以了。

我使用的是非GitHub官方的主题，使用 `remote_theme: cayman`。
