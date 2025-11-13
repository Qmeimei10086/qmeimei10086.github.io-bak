---
layout: post
title: "安卓逆向反混淆追踪工具-ZenTracer修复与更新"
author: "Qmeimei10086"
header-style: text
tags:
  - 逆向
  - 安卓
---

# 仓库地址
https://github.com/Qmeimei10086/ZenTracer/

# 安装
由于各个版本frida存在api差异，推荐使用conda构建隔离环境  
## 1. 安装conda
## 2. 创建虚拟环境
```javascript
conda create -n frida16 python=3.8

```
## 3.配置依赖
```javascript
pip install frida==16.4.2 -i https://pypi.tuna.tsinghua.edu.cn/simple
#去git下载对应版本的frida-server
pip install frida-tools==12.4.4 -i https://pypi.tuna.tsinghua.edu.cn/simple
pip install PyQt5
```

