---
layout: post
title:  "《JavaScirpt高级程序设计》读书笔记"
date:   2017-06-25 14:20:40 +0800
categories: 技术
---

> 记录书上的一些知识点，方便自己查阅。顺便记录自己的阅读历程。排版上就不太严格要求了。另外，没有按照书本的目录来阅读，而是想补充的知识先看，所以每个章节的阅读时间不是升序排列的。

(20170626)
### 第13章 事件
JavaScript 与 HTML 之间的交互是通过事件实现的。事件，就是文档或浏览器窗口中发生的一些特定的交互瞬间。
事件流描述的是从页面中接收事件的顺序。在单击按钮的同时，你也单机了按钮的容器元素，甚至也单击了整个页面。
IE的事件流叫做事件冒泡 event bubbling，即事件开始时由最具体的元素接收，然后逐级向上传播到较为不具体的节点。
Netscape Communicator 团队提出的另一种事件流叫做事件捕获 event capturing 。与事件冒泡相反，建议优先采用事件冒泡。
DOM2事件流：事件捕获阶段、处于目标阶段和事件冒泡阶段。
响应事件的函数就叫做事件处理程序。事件处理程序的名字以 `on` 开头。

要阻止特定事件的默认行为，可以使用preventDefault()方法。

DOM3级事件规定的几类事件
* UI事件，当用户与页面上的元素交互时触发
* 焦点事件，当元素获得或失去焦点时触发
* 鼠标事件，当用户通过鼠标在页面上执行操作时触发
* 滚轮事件，当使用鼠标滚轮时触发
* 文本事件，当在文档中输入文本时触发
* 键盘事件，当用户通过键盘在页面上执行操作时触发
* 合成事件，当为IME(Input Method Editor)输入字符时触发
* 变动事件，当底层DOM结构发生变化时触发9

(20170625)
### 第14章 表单脚本

取得 **form** 元素的引用方式有好几种。最常见的：`var form = document.getElementById("form1");`

获取页面中所有的表单：`document.forms`

再通过索引或者 **name** 值来取得特定的表单：

`var firstForm = document.forms[0];`

`var myForm = document.forms["form2"];`

可以同时为表单指定id和name属性，但是它们的值不一定相同。

使用 **input** 或 **button** 都可以定义提交表单按钮，只要将其type特性设置为 _submit_ 即可。**image** 也是可以的，type特性设置为 _image_。

浏览器会在将请求发送给服务器之前触发 _submit_ 事件。阻止这个事件的默认行为就可以取消提交表单。在表单数据无效而不能发送给服务器时，可以使用这一技术。

`var form = document.getElementById("myForm");
EventUtil.addHandler(form,"submit",function(event){
    event = EventUtil.getEvent(event);
    EventUitl.preventDefault(event);
});`

以编程方式提交表单：`form.submit();`这种方法不会触发 _submit_ 事件。

**input**、**button** type 为 reset 时重置表单

`form.reset()` 重置表单，会触发 _reset_ 事件。

**可以动态修改表单字段属性**