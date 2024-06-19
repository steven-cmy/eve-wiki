---
title: 国内Discord使用教程及帮助
description: 
published: true
date: 2024-06-19T17:04:06.466Z
tags: 
editor: markdown
dateCreated: 2024-06-19T04:29:24.639Z
---

Discord是一款闭源免费的实时通话聊天软件，主要用于游戏玩家，因其简单易用功能丰富而被广泛使用。

由于某些原因，这款软件在国内被屏蔽，方法主要是DNS污染，2019年国庆后又新增了新的未知拦截方式（疑似TLS握手阻断）。\*\*现在除了膜法以外暂无稳定解限的办法。\*\*有些地区可以通过修改host直接访问，而在有些封锁严重的地区需要同时使用反代/魔法来使用，各地区的封锁也在不断变换，有可能每隔一段时间就会更换封锁手段。

## 解除限制

以下是几种常见方法：

### 使用UsbEAm Hosts Editor

这是一款由Dogfight360大神开发的软件，旨在消除游戏玩家面对的不必要的DNS污染。现新加入反代功能。需要注意的是这里的反代功能大陆大部分地区无法使用，本意是为网络速度过慢的地区加速登录更新用的。

首先前往[作者博客](https://www.dogfight360.com/blog/475/)下载最新版。

下完后解压至任意目录。

右键用管理员权限运行主程序

![](/assets/images/discord_tutorial/usbeam_tut_1.png)

点击左下角手柄按钮并选择\[Discord – 语音&游戏平台\]>\[Discord登录/更新/加载/图片/游戏下载\]（或者要使用作者的反代服务器的话请选择\[Reverse Proxy – 反代加速（游戏平台）\]>\[Discord\]）

![](/assets/images/discord_tutorial/usbeam_tut_2.png)

左侧会列出所有可用的正常DNS解析服务器。然后点击检测延迟。（注：你的延迟会跟截图不一样，选择最低的即可）

![](/assets/images/discord_tutorial/usbeam_tut_3.png)

检测延迟并选择最低的那个，点击应用选中host就编辑完成了。（可点击编辑Host确认）

![](/assets/images/discord_tutorial/usbeam_tut_4.png)

![](/assets/images/discord_tutorial/host_example.png)

### 使用steamcommunity 302

Dogfight360大神编写的另一个软件。虽然本意是解锁Steam社区但是也加入了Discord反代功能，在host方法被封的现状下，这个方法应该是最简单的。**需要注意的是因为此软件会安装作者自己签发的CA根证书，所以可能会造成安全隐患（例如**[**中间人攻击**](https://zh.wikipedia.org/wiki/%E4%B8%AD%E9%97%B4%E4%BA%BA%E6%94%BB%E5%87%BB)**），是否使用请自行判断！**

下载地址：[https://www.dogfight360.com/blog/686/](https://www.dogfight360.com/blog/686/) （下载文件可能会被浏览器拦截，因为使用了第三方证书）

使用方法非常简单，打开设置勾选Discord后直接启动服务并且按照屏幕指示安装证书并允许通过防火墙即可。

![](/assets/images/discord_tutorial/steamcommunity_302_设置界面.jpg)

如有问题请参考博客下方的常见问题解决方案。

### 使用Watt Toolkit（原Steam++）

Watt Toolkit瓦特工具箱（原名Steam++）是一个开源跨平台的多功能 Steam 工具箱，可使Steam社区、Github、谷歌验证码等国内难以访问的网页正常访问，同时解决打开Discord之后软件一直卡在更新状态的这种情况。**需要注意的是因为此软件会安装作者自己签发的CA根证书，所以可能会造成安全隐患（例如**[**中间人攻击**](https://zh.wikipedia.org/wiki/%E4%B8%AD%E9%97%B4%E4%BA%BA%E6%94%BB%E5%87%BB)**），是否使用请自行判断！同时，此软件的某些功能可能会违反EULA/ToS从而导致严重后果，使用前请先阅读并理解其风险（**[**https://steampp.net/faq#SecurityRisk**](https://steampp.net/faq#SecurityRisk)**）。**

软件官网：[https://steampp.net/](https://steampp.net/)

软件Github：[https://github.com/BeyondDimension/SteamTools/releases/](https://github.com/BeyondDimension/SteamTools/releases/)

### 手动编辑Host文件

此方法约等于使用UsbEAm Hosts Editor。

直接修改host文件：

`C:\Windows\System32\drivers\etc\hosts`

添加或替换以下内容：

```plaintext
1.0.0.1 discordapp.com
1.0.0.1 dl.discordapp.net
1.0.0.1 gateway.discord.gg
1.0.0.1 status.discordapp.com
1.0.0.1 support.discordapp.com
1.0.0.1 cdn.discordapp.com
1.0.0.1 media.discordapp.net
1.0.0.1 images-ext-2.discordapp.net
1.0.0.1 images-ext-1.discordapp.net
1.0.0.1 discordcdn.com
1.0.0.1 discord.com
```

其中1.0.0.1可更换为任意能够访问且没被污染的DNS服务器或反代服务器。*注：Win7、Win8、Win10等系统可能需要管理员权限才可修改host，只需将Host文件先复制到桌面用记事本打开，修改并保存后将文件粘贴覆盖源文件。*

### 魔法上网

膜法就不教了，网上教程多的是，这应该是最好（但不是最简单/便宜）的解决办法了。

[单独代理Discord的方法在这里](https://web.archive.org/web/20201026103058/https://zhuanlan.zhihu.com/p/47048247)

## 下载及注册账号

![](/assets/images/discord_tutorial/discord注册界面.png)

Discord注册界面

解除限制后就可以下载软件了。

前往[官网](https://discord.com/download)或群文件下载安装程序并运行。

更新完成后进入登录界面点击下方注册按钮。

填入相应信息并注册然后记得验证邮箱。

这样Discord账号的注册就完成了，强烈建议使用高强度密码并且设置两步验证以防账号丢失。

## 使用说明

Discord有中文界面。创建服务器也是完全免费的。权限系统简单明了。

[官方教程](https://support.discord.com/hc/zh-tw)大部分是英文或者繁中，看不懂的话就去[B站找视频](https://search.bilibili.com/all?keyword=discord)吧。

还是不会的话可以看[这里](https://btfy.ur1.fun/?q=ZGlzY29yZOaAjuS5iOeUqA==)。

![](/assets/images/discord_tutorial/discord界面-1024x722.png)