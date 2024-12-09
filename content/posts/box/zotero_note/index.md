---
title: "Zotero笔记同步"
date: 2023-08-28
tags: ["Zotero"]
categories: ["好玩的工具"]
draft: false
---
## Zotero笔记配置
zotero作为一个开源的文献管理工具，当我们对其进行基本配置之后，就可以开始用它读文献啦。这个"基本配置"主要包括云空间同步设置以及以下必要插件的安装：
- [Better BibTex](https://retorque.re/zotero-better-bibtex/)
- [markdown here](https://github.com/adam-p/markdown-here)
- [Better BibTex](https://retorque.re/zotero-better-bibtex/)
- [zotero translator](https://retorque.re/zotero-better-bibtex/)
  
但当我们愉快地写完笔记，用另一台设备打开时，却发现笔记内容只有文字同步过来，而照片却没有显示。这是因为插入笔记的图片被保存在本地而并未上传，所以，若想将笔记完全迁移到其他设备只能将图片也一并复制过去，这无疑不是一个聪明的办法。
事实上，如果我们首先将图片上传，本地图片变为在线图片，再插入到Markdown文档不就可以在不同的设备上显示了嘛！
而上面提到的这个过程，也正是 `图床` 的功能。

## 图床

> 图床一般是指储存图片的服务器，我们用这个服务器托管我们的图片，就可以直接获得图片的网络地址，然后我们在 `.md` 文本中使用网络地址，这样图片就可以在网页上加载出来了！

这里我们选择 [PicGo](https://imgloc.com) 作为我们的图床工具，我们可以通过它上传和管理图片，而且他支持许多平台，如[Chevereto](https://github.com/MYXXTS/Chevereto-Upload)、[GitHub](https://github.com/)、阿里云、腾讯云等。

首先根据 [PicGo客户端下载流程](https://imgloc.com/page/client) 安装好 PicGo。当然在此之前需要先按照指引注册以获取秘钥。这里不再赘述。