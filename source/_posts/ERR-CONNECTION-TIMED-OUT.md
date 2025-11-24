---
title: ERR_CONNECTION_TIMED_OUT
date: 2023-04-18 00:00:12
categories:
- Debug
tags:
- 浏览器
---

  

> solvesolvesolve NP incomplete
>
> errorerrorerror I'm irrational
>
> ---《Debug之歌》

在墙外惦记着vpn+netflix嫖全世界电影的下场（

再一次被学校服务器拒绝了，并出现ERR_CONNECTION_TIMED_OUT

![ERR_CONNECTION_TIMED_OUT error in Chrome](https://kinsta.com/wp-content/uploads/2019/07/ERR_CONNECTION_TIMED_OUT-error-in-chrome.png)



#### 解决：刷新/更新DNS

> 你可以尝试刷新本地DNS缓存。这类似于清除浏览器缓存。可能是因为你正在尝试访问的网站没有解析到正确的IP地址。如果你刚刚将WordPress网站迁移到新主机，等待所有事情完全传播是非常重要的。这有时可能需要长达24小时，虽然有时只需几分钟。这取决于你的DNS提供商和DNS记录的TTL值。
>
> ---chatgpt

在Windows中，只需打开命令提示符（win键+R，输入cmd回车）并输入以下内容：

```
ipconfig /flushdns
```

 

