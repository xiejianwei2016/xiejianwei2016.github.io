---
layout: post
title:  使用adb命令去访问app数据库内容
date:   2016-12-23 17:10:00 +0800
categories: Android
tag: SQLite
---

* content
{:toc}



具体步骤如下：
=======================================

1.连上已经root的手机或者模拟器 运行
-----------------------------------------------

	adb devices//确保可以找到当前设备   且只能是一个
	adb shell

2.进入到需要查看数据库的安装包路径下
-------------------------------------

	#cd   data/data/packagename(com.example.test)
	#ls //列出当前目录下文件列表
    #cd  databases  //进入到数据库文件夹 可继续 #ls
    #sqlite3  databaseFileName//访问对应数据库文件名
	#select * from   databaseName //查找数据库名字对应所有存储数据内容

3.总结
----------------------------

不要惧怕命令行，要敢于尝试，反正输入错了又不会怎样，重新输入对的就好了。jsut do  it!

其它有用的adb shell  命令
===============================
adb push（拷贝文件去手机终端）
--------------------

Upload a specified file from your computer to an emulator/device.

	adb push <local> <remote>
	adb push test.apk /sdcard

Copies <android-sdk-path>/platform-tools/test.apk to /sdcard directory.

	adb push d:\test.apk /sdcard

Copies d:\test.apk to /sdcard directory.

+ 更多命令：[adb shell 官网](http://adbshell.com/)