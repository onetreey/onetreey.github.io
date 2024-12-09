---
title: "hugo 博客搭建纪要"
date: 2023-05-16T15:01:06+08:00
tags: ["hugo","github"]
categories: ["有趣的知识"]
draft: false
---

首先需要 `hugo` 建立站点，
然后 `hugo server` 查看本地博客，作为一个预览。

```bash
   hugo
   hugo server
```
之后需要将本地博客推到远端库，具体而言：
 
```bash
   git init                         #重置 `.git` 库
   git add .                        #添加文件
   git commit -m  "说明文字"         #提交
   git status                       #查看状态
   git push -u origin master        #推到远端库
```
假如更新被拒绝，因为远程仓库包含本地尚不存在的提交。通常会有一个这样的提示：`一个仓库已向该引用进行了推送`。再次推送前，可能需要先整合远程变更,然后再次推送:

```bash
   git pull
   git push
```
推送失败的话可以尝试以下命令：

```bash
   git push -u origin main -f
```
推送成功之后，正常情况下站点会自动同步更新（在`github pages`已打开的情况下），但假如代码书写不规范或者不够简洁，则可能导致站点无法建立（即使本地博客预览是正常的），此时需要到 [github](https://github.com) 目标仓库的 `actions`查看 `pages-build-deployment`,根据提示修改相应的代码，之后重新推送。

有其他问题直接复制报错百度。

另外，全局设置要注意的是：

 ```bash
    git config -global user.name ""
    git config -global user.email ""
 ```  
