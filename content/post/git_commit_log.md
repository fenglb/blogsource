---
title: "Git 提交日记规范化"
date: 2020-05-18T20:52:19+08:00
lastmod: 2020-05-18T20:52:19+08:00
draft: false
keywords: [Git]
description: "关于 Git 的提交日记内容形式规范化"
tags: [git]
categories: [开发技术]
author: "冯柳宾"
---

传统的 Git 提交约定形式
<!--more-->

```
$ git log --oneline ./src/components/button/

06faab4d revert: feat: add disabled property
186cce90 feat: add disabled property
5b998d9a test: add scenario for readonly property
263288a5 fix: fix css when hover
c3fb85af feat: add button component
```
提交的类型:

* feat: Add a new feature 新功能: 添加一个新特性
* fix: Fix a bug 修复: 修复一个 bug
* docs: Documentation changes. 文档: 文档变更
* style: Code style change (semicolon, indentation…). Style: 代码样式更改(分号、缩进...)
* refactor: Refactor code without changing public API. Refactor: 在不更改公共 API 的情况下重构代码
* perf: Update code performances. Perf: 更新代码性能
* test: Add test to an existing feature. 测试: 将测试添加到现有特性中
* chore 杂务: Update something without impacting the user (ex: bump a dependency in : 在不影响用户的情况下更新某些内容(例如: 在package.json).
