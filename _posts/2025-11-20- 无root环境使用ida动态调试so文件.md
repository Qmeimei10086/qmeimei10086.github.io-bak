---
layout: post
title: " 无root环境使用ida动态调试so文件"
date:       2025-11-20
author: "Qmeimei10086"
header-style: text
tags:
  - CTF
  - 逆向
  - 安卓
---

# 起因
前几天打vctf时候遇到一道需要动调的安卓题，但是在雷电模拟器调了半天有问题，后面查到估计是雷电是吧arm的so的指令、转译为x86的指令了，所以动调的时候会有问题。但是我的安卓测试机还没到，所以去查了无root动态调试的方法（我自己的手机没root），遇到一些坑，这里做个记录
# 步骤
## 1.修改权限
网上查到的方法缺少关键一步就是给app网络访问权限，否则ida-server在启动会报错  
用mt管理器打开AndroidManifest.xml
在<manifest>标签下添加
```xml
<uses-permission android:name="android.permission.INTERNET" />
#找到application 标签，添加运行debug权限：
android:debuggable=“true”
```
然后安卓
## 2. 启动ida-server

1. adb shell进入shell   
2. adb push android_server /data/data/包名目录    
3. run-as 包名  
4. chmod 777 android_server  
5. ./android_server  
6. adb forward tcp:23946 tcp:23946  
然后就愉快的附加调试吧