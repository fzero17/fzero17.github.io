---
title: iCloud Drive 显示 App 文件夹
date: 2021-02-03 11:08:27
tags:
---
要想在 iCloud Drive 中显示App的文件夹，很简单，只要下面这两步操作。

- 在设备上登陆苹果账号，并开启同步功能。

- 在 `Info.plist` 中设置以下内容：

```
<key>NSUbiquitousContainers</key>
    <dict>
        <key>iCloud.com.example.MyApp</key>
        <dict>
            <key>NSUbiquitousContainerIsDocumentScopePublic</key>
            <true/>
            <key>NSUbiquitousContainerSupportedFolderLevels</key>
            <string>Any</string>
            <key>NSUbiquitousContainerName</key>
            <string>MyApp</string>
        </dict>
    </dict>

```

> 来源：[Enabling Document Storage in iCloud Drive](https://developer.apple.com/library/archive/documentation/General/Conceptual/iCloudDesignGuide/Chapters/DesigningForDocumentsIniCloud.html#//apple_ref/doc/uid/TP40012094-CH2-SW20)

在具体操作时可能会遇到下面的一些问题：

- 文件夹不在 iCloud Drive 中显示
- 同步的音频文件无法正常播放

按照下面的方法可以解决

`修改Build版本号，重新运行`。

> 来源：
>
> [在 iCloud Drive中显示 App的iCloud文件夹](https://arc-lin.github.io/2016/10/29/cj66ozfny0039b7fyfvx6dm35/)
>
> [StackOverflow](https://stackoverflow.com/questions/30385940/why-my-app-is-not-shown-in-icloud-drive-folder)





最后，还有一个问题：文件夹不在没有运行App的设备的 iCloud Drive 中显示。
