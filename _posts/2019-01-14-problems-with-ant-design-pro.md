---
layout: post
title:  "使用 Antd 时遇到的问题"
date:   2019-01-14 18:10:40 +0800
categories: life
---

今天拿到了一个新项目的源代码，是使用 Ant Design Pro 构建的，下到本地 npm install 之后，npm start 总是报错：

```
Cannot resolve module in ./node_modules/require-from-string/index.js, ./node_modules/resolve-from/index.js

```

检查了很久，最后一项一项的比较依赖，发现是 postcss-loader 引起的问题，搜索了一下发现项目中没有使用这个库，删除掉这个依赖就没有问题了。