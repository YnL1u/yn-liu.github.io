---
title: "GitHub Pages + Jekyll 搭建个人网站：从 0 到上线的完整踩坑记录"
date: 2026-03-15
categories: [Blog]
tags: [Jekyll, GitHub Pages, Web, 踩坑记录]
---


## 一、为什么要搭建个人网站

作为软件工程专业学生，我希望拥有一个可以长期展示：

- 项目经历（Portfolio）
- 技术博客（Blog）
- 学习记录
- 技术成长轨迹

相比第三方博客，GitHub Pages + Jekyll 有几个优势：

- 免费托管
- 与 GitHub 项目直接绑定
- 支持 Markdown 写作
- 适合长期维护

于是开始了个人网站搭建之路。

---

## 二、整体技术架构

网站实际运行流程如下：
GitHub Repository
↓
GitHub Pages
↓
Jekyll 静态生成
↓
HTML 页面发布

核心原理：

> Markdown → Jekyll 编译 → 静态 HTML → 网站页面

---

## 三、第一个坑：直接在 GitHub 修改文件

一开始我一直在 GitHub 网页端直接修改代码。

结果出现：

- 页面布局突然异常
- Portfolio 页面内容消失
- 不知道误删了什么文件

原因是没有本地开发环境。

### 正确方式
GitHub clone → 本地修改 → 本地预览 → push

---

## 四、正确开发流程（重要）

### 1. 克隆仓库

git clone 仓库地址.git；
等待下载完成就储存在本地了，使用vs打开即可

### 3. 本地运行 Jekyll

在 VSCode 终端运行：

```bash
bundle install
bundle exec jekyll serve
```

浏览器打开：
http://localhost:4000

现在修改 Markdown 文件后，网页会自动刷新，可以实时预览效果。

---

### 4. VSCode 终端提交代码

完成修改后，可以直接在 VSCode 终端上传到 GitHub。

首先查看文件状态：

```bash
git status
```

添加所有修改文件：

```bash
git add .
```

提交修改：

```bash
git commit -m "update website"
```

最后推送到 GitHub：

```bash
git push
```

如果 push 成功，GitHub Pages 会自动重新构建网站，几分钟后即可在网页上看到更新内容。

---
