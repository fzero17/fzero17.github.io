---
title: ElementUI 表单验证
date: 2024-04-26 15:05:34
tags: 技术
---

在后台管理项目中，表单是一个经常使用的组件，为了在以后的项目中能够更加高效地实现表单功能，这里记录一下在 Vue 项目中使用 element-ui 的 Form 组件时，对表单进行验证的方法。

一、基本使用

> 可以做一些简单的验证，如必填、长度限制等。

```javascript
<template>
<el-form>
    <el-form-item label="用户名" prop="username">
        <el-input v-model="form.username"></el-input>
    </el-form-item>
    <el-form-item label="密码" prop="password">
        <el-input v-model="form.password"></el-input>
    </el-form-item>
</el-form>
</template>

<script>
export default {
    data() {
        return {
            form: {
                username: '',
                password: ''
            },
            rules: {
                username: [
                    { required: true, message: '请输入用户名', trigger: 'blur' }
                ],
                password: [
                    { required: true, message: '请输入密码', trigger: 'blur' }
                ]
            }
        }
    }
}
</script>
```

二、validator

> 可以做一些复杂的验证，如正则验证、自定义验证等。

```javascript
<template>
<el-form :model="form" :rules="rules">
    <el-form-item label="用户名" prop="username">
        <el-input v-model="form.username"></el-input>
    </el-form-item>
    <el-form-item label="密码" prop="password">
        <el-input v-model="form.password"></el-input>
    </el-form-item>
</el-form>
</template>
<script>
export default {
    data() {
        return {
            form: {
                username: '',
                password: ''
            },
            rules: {
                username: [
                    { required: true, message: '请输入用户名', trigger: 'blur' },
                    { min: 3, max: 5, message: '长度在 3 到 5 个字符', trigger: 'blur' }
                ],
                password: [
                    { required: true, message: '请输入密码', trigger: 'blur' },
                    { validator: this.validatePassword, trigger: 'blur' }
                ]
            }
        }
    },
    methods: {
        validatePassword(rule, value, callback) {
            if (value === '') {
                callback(new Error('请输入密码'));
            } else {
                if (value.length < 6) {
                    callback(new Error('密码长度不能小于 6 位'));
                } else {
                    callback();
                }
            }
        }
    }
}
</script>
```

三、表单列表验证

> 验证表单列表。例如，验证每一行的输入框是否为空。

```javascript
<template>
<el-form :model="form" :rules="rules">
    <el-form-item v-for="(user, index) in users"
    :key="index"
    label="用户名"
    :prop="users.${index}.username"
    :rules=[{required: true, message: '请输入用户名', trigger: 'blur'}]
    >
        <el-input v-model="user.username"></el-input>
    </el-form-item>
</el-form>
</template>
<script>
export default {
    data() {
        return {
            users: [
                {username: '', password: '' },
            ]
        }
    }
}
</script>
```
