---
layout: post
title: 在Ubuntu 16.04下用脚本一键安装ShadowsocksR
category: 技术
tags: ShadowsocksR
description: 主要用于浏览器（火狐和谷歌）正常上网
---

### 转自：https://www.djangoz.com/2017/08/16/linux_setup_ssr/

### 该脚本会运行git命令，所以前提先安装git
  
    sudo apt-get install git

### 脚本安装ShadowsocksR

    wget http://www.djangoz.com/ssr
    sudo mv ssr /usr/local/bin
    sudo chmod 766 /usr/local/bin/ssr
    ssr install

### 配置
    
    ssr config

### 设置开机自启动

sudo vim /etc/rc.local

   在文末添加：
     sudo ssr start
     exit 0
    若开机没有自动启动，可能是当前用户权限不够，不能执行。若没有安全顾虑，简单粗暴添加权限就好了：sudo chmod 0774 /etc/rc.local

### 相关操作

  启动：sudo ssr start
  关闭：sudo ssr stop
  重启：sudo ssr restart
  
### 浏览器安装SwitchyOmega插件
  以火狐为例
  在添加组件——>获取附加组件中搜索SwitchyOmega插件，安装，新建情景模式，填好相关信息（端口填的是你ssr配置文件中填的本地端口号）

