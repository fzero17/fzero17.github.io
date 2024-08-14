---
layout: 修改安装
title: 修改etherpad-lite插件的npm源
date: 2024-08-14 09:08:13
tags:
---

将etherpad-lite部署到服务器后，插件需要通过npm安装，由于服务器无法访问境外网站而安装失败，

花了两天时间绕了一大圈去解决这个问题，耗费了不少精力。

后来和AI一起阅读代码发现一行很简单的代码可以解决安装的问题。

在`src/static/js/pluginfw/LinkInstaller.ts`文件中，将`npm`的源地址改为`https://registry.npmmirror.com`即可。

```typescript
this.livePluginManager = new PluginManager({
            npmRegistryUrl: 'https://registry.npmmirror.com/',
            pluginsPath: pluginInstallPath,
            hostRequire: undefined,
            cwd: path.join(settings.root, 'src')
        });
```
