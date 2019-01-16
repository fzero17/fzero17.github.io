---
layout: post
title: "rem"
date: 2019-01-16 11:21:40 +0800
categories: css3
---

今天看 css 文章时，学习到了一个新的概念： rem （_原谅现在的我这么孤陋寡闻_）。文章中并没有解释 rem 是什么，于是自己 Google 学习一下，做点笔记。

### 什么是 REM

在 MDN 的 [CSS 的值和单位](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Values_and_units) 这篇文章中介绍了 rem ：

> REM（root em）和 em 以同样的方式工作，但它总是等于默认基础字体大小的尺寸；继承的字体大小将不起作用，所以这听起来像一个比 em 更好的选择，虽然在旧版本的 IE 上不被支持

所以，rem 其实就是一个单位。

### REM 的用法

在张鑫旭大大的这篇[基于 vw 等 viewport 视区单位配合 rem 响应式排版和布局
](https://www.zhangxinxu.com/wordpress/2016/08/vw-viewport-responsive-layout-typography/)中，讲到了 vw + rem 的用法，代码中并没有出现 rem 这个单位。所以有些情况下只需要给 root 元素定义好大小即可。（_不知道这样理解是否有误_）

另外在 MDN 上 [How can we design for all types of users？](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Design_for_all_types_of_users) 这篇文章中，列举了 rem 的用法，如下。

HTML 代码

```html
<!DOCTYPE html>
<html lang="zh">
  <head>
    <meta charset="UTF-8" />
    <title>Font size experiment</title>
  </head>
  <body>
    <h1>
      This is our main heading
      <span class="subheading">This is our subheading</span>
    </h1>
  </body>
</html>
```

CSS 代码

```css
body {
  font-size: 1em;
} /* 1em = 100% of the browser's base font size, so in most cases this will render as 16 pixels */
h1 {
  font-size: 2rem;
} /* twice the size of the body, thus 32 pixels */
span.subheading {
  font-size: 1rem;
} /* original size */
```

### REM 的用途

针对不同屏幕的适配，可以使用 rem。

### 参考资料

[CSS 的值和单位](https://developer.mozilla.org/zh-CN/docs/Learn/CSS/Introduction_to_CSS/Values_and_units)

[How can we design for all types of users？](https://developer.mozilla.org/en-US/docs/Learn/Common_questions/Design_for_all_types_of_users)

[基于 vw 等 viewport 视区单位配合 rem 响应式排版和布局
](https://www.zhangxinxu.com/wordpress/2016/08/vw-viewport-responsive-layout-typography/)

[移动 web 适配利器-rem](http://www.alloyteam.com/2016/03/mobile-web-adaptation-tool-rem/)
