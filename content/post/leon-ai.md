---
title: "Leon AI-开源的个人助理"
date: 2019-05-03T20:00:09+08:00
lastmod: 2019-06-07T15:30:00+08:00
draft: false
keywords: [Leon, AI]
description: "开源的个人助理"
tags: [Leon]
categories: [深度学习]
author: "冯柳宾"
---

[leon](https://getleon.ai)一个开源的个人助理，可以训练成自个的智能助理软件。
<!--more-->

一直以来，我就想搭建自己的语音智能助理，但是有不喜欢商业的语音助理，比如Siri，OK Google，小度，小易等等，觉得控制权在开发商那边，数据也在他们那边，没有任何控制权和隐私权。

leon这个项目，可以拿来玩玩。

以下是我翻译leon的的词汇表.

# 词汇表

你也许不认识一些文档中的词汇;这篇文章将有助于您更好理解这些词汇已经它们和Leon的关系.

## 操作 <Badge text="1.0.0-beta.3+"/>

操作作为切入口.
        
> Attachment: [packages/calendar/todolist.py](https://github.com/leon-ai/leon/tree/develop/packages/calendar/todolist.py) *example of the `To-Do List` module including actions such as `create_list`, `complete_todo`, etc*.

## API

API代表*应用程序编程接口*，它允许项目的不同节点之间进行通信。这些节点可以是服务器、库等。

Leon APIs 的例子:
- [HTTP API](https://github.com/leon-ai/leon/tree/develop/server/src/api) 服务器和客户端数据交换.
- [WebSocket API](https://github.com/leon-ai/leon/blob/develop/server/src/core/server.js) 服务器和客户端双向通讯通道.
- [Python library API](https://github.com/leon-ai/leon/blob/develop/bridges/python/utils.py) 允许开发者自定义函数调用Leon的模块.

## ASR

ASR或*自动语音识别*是利用计算机硬件和软件技术来识别和处理人类语音。

Leon使用这个模块来识别语音.

> Attachments:
> - [app/js/main.es6.js](https://github.com/leon-ai/leon/blob/develop/app/js/main.es6.js) *ASR web app*.
> - [server/src/core/asr.js](https://github.com/leon-ai/leon/blob/develop/server/src/core/asr.js) *ASR server*.

## Answers

Answers 是 Leon 的应答模块.
Each [package](/glossary.md#packages) has its own set of answers with different translations.
每个包[package](#package)都包含它们自个的 answers 模块, 这个模块具有不同翻译版本.

> Attachment: [packages/checker/data/answers/en.json](https://github.com/leon-ai/leon/blob/develop/packages/checker/data/answers/en.json) *example of the `Checker` package English answers*.

## Brain

Leon 的 Brain 是它的核心部分, 负责执行[modules](#modelus), 应答, 理解语句等等.

> Attachment: [server/src/core/brain.js](https://github.com/leon-ai/leon/blob/develop/server/src/core/brain.js) *Leon's brain*.

## Classifier

分类器是一种模型, 一旦经过训练可以通过算法输出一个结果, 这个结果将用于做出决定.

Leon 使用它来存储[expressions](#expressions)训练输出的结果.

## Expressions

Expressions 是 Leon 用来训练理解能力的数据集合.
每一个[package](#packages)都拥有自个不同语言版本的训练集.

> Attachment: [packages/checker/data/expressions/en.json](https://github.com/leon-ai/leon/blob/develop/packages/checker/data/expressions/en.json) *example of the `Checker` package English expressions*.

## Modules

Modules are Leon's skills; thanks to them Leon can work his magic. Modules contain one or an infinity of [actions](/glossary.md#actions).
Modules 是 Leon 的技巧; 由于它们 Leon 才能发挥它的功能. Modules 可以包含一个或者无限个[actions](#actions).

::: 提示
越多的 models, Leon功能将越强大.
欢迎来添加贡献[contribute](https://github.com/leon-ai/leon/blob/develop/.github/CONTRIBUTING.md) <3

:::

## NLU

NLU (*自然语言理解*) 帮助计算机理解人类语言.

Leon 利用它来加载最合适的方法[classifier](#classifier).
> Attachment: [server/src/core/nlu.js](https://github.com/leon-ai/leon/blob/develop/server/src/core/nlu.js) *Leon's NLU*.

## Packages

Leon 的 packages 包含一个或者无限个[modules](#modules). 你可以认为 packages 就是 modules 的集合. 这是 [answers](#answer) 和 [expressions](#expressions)保存的地方.

> Attachment: [packages/leon](https://github.com/leon-ai/leon/tree/develop/packages/leon) *example of the `Leon` package including modules related to Leon himself*.

::: 提醒
完整的 package 清单在[这里](https://github.com/leon-ai/leon/tree/develop/packages).
:::

## STT

STT, *语音转文字*, 把语言转换成文字.

Leon has multiple STT parsers; you can choose one (or several) to [configure](/configuration.md#voice).
Leon 有多个 STT 过滤器; 你通过[configure](https://github.com/leon-ai/leon/configuration.md#voice)可以选择其中一个或者数个.

> Attachment: [server/src/stt/stt.js](https://github.com/leon-ai/leon/blob/develop/server/src/stt/stt.js) *Leon's STT*.

## Synchronizer

synchronizer 可以同步内容到云端或者您的设备(Google Drive等). 主要有[moduels](#modules)配置.

可以根据您的偏好来在[configure](https://github.com/leon-ai/leon/configuration.md#synchronizer)为每个 module 设置来支持这个功能. 

> Attachment: [server/src/core/synchronizer.js](https://github.com/leon-ai/leon/blob/develop/server/src/core/synchronizer.js) *Leon's synchronizer*.

## TTS

TTS 或者 (*文字转语音*) 把文字转换为音频输出.

Leon 有多个 TTS synthesizers; 你可以在[configure](https://github.com/leon-ai/leon/configuration.md#voice)设置.

> Attachment: [server/src/tts/tts.js](https://github.com/leon-ai/leon/blob/develop/server/src/tts/tts.js) *Leon's TTS*.

### HOME ASSISTANT

Home Assistant 是一个运行在 Python 3上的开源家庭自动化平台, 跟踪和控制所有设备在家里和自动化控制。
