---
layout: post
title: "Vim Plugin"
category: tools 
tags: [vim]
description: |
  Vim is a text editor written by Bram Moolenaar and first released publicly in 1991. Based on the vi editor common to Unix-like systems, Vim is designedfor use both from a command line interface and as a standalone application in a graphical user interface.
---
{% include JB/setup %}

[Vim](http://www.vim.org/).

##Shortcut Key 
###tags
CTRL-]                  "跳转到当前光标下的标签
CTRL-T                  "跳到标签栈中较早的标签 

###cscope
**s: 查找C语言符号，即查找函数名、宏、枚举值等出现的地方**
**g: 查找函数、宏、枚举等定义的位置，类似ctags所提供的功能**
**d: 查找本函数调用的函数**
**c: 查找调用本函数的函数**
**t: 查找指定的字符串**
**e: 查找egrep模式，相当于egrep功能，但查找速度快多了**
**f: 查找并打开文件，类似vim的find功能**
**i: 查找包含本文件的文件**
**<C-_ >g 的按法是先按"Ctrl+Shift+-", 然后很快再按"s/g/d/c....."**

###quickfix 
**:cw**

###书签
**创建书签：CTRL+F2**
**正向切换：F2**
**反向切换：SHIFT+F2**

###高亮
**",hl" 高亮书签**
**",hh"清除高亮书签**
**第一次用 `,#`  `,*` 上下搜索，以后直接用`*` `#`**

###折叠 
**za 打开/关闭当前折叠**
**zA 循环地打开/关闭当前折叠**
**zM 关闭所有折叠**
**zR打开所有折叠**

###查找
**F5 全局查找".h/.c/.java/.."文件**
**F3 本文件查找**
**F4 全局查找**

###补全
**Ctrl+X Ctrl+L 整行补全**
**Ctrl+X Ctrl+N 根据当前文件里关键字补全**
**Ctrl+X Ctrl+K 根据字典补全**
**Ctrl+X Ctrl+T 根据同义词字典补全**
**Ctrl+X Ctrl+I 根据头文件内关键字补全**
**Ctrl+X Ctrl+] 根据标签补全**
**Ctrl+X Ctrl+F 补全文件名**
**Ctrl+X Ctrl+D 补全宏定义**
**Ctrl+X Ctrl+V 补全 vim 命令**
**Ctrl+X Ctrl+U 用户自定义补全方式**
**Ctrl+X Ctrl+S 拼写建议**

##Vim Plugin
[taglist](http://www.vim.org/scripts/script.php?script_id=273)  
列出了当前文件中的所有宏, 全局变量, 函数名等，类似source Insight左边的Symbol窗口.  
[WinManger](http://www.vim.org/scripts/script.php?script_id=95)  
文件浏览器,通过这个浏览器来浏览工程中的源文件.  
[MiniBufExplorer](http://www.vim.org/scripts/script.php?script_id=159)  
在一个Vim窗口打开多个标签.  
[a.vim](http://www.vim.org/scripts/script.php?script_id=31)  
.h/.c文件相互切换.  
[Grep](http://www.vim.org/scripts/script.php?script_id=311)  
对光标所在单词全工程的grep.  
[VisualMark](http://www.vim.org/scripts/script.php?script_id=1026)  
书签高亮功能.  
[SuperTab](http://www.vim.org/scripts/script.php?script_id=1643)  
快速自动补全代码功能，需要开启 new-omni-completion.  
[echofunc](http://www.vim.org/scripts/script.php?script_id=1735)  
在插入模式下,输入函数名字后在输入一个`(`,显示函数原型.  
[Lookupfile](http://www.vim.org/scripts/script.php?script_id=1581)  
输入部分的文件名，找到符合条件的工程中的文件.  
[snipMate](http://www.vim.org/scripts/script.php?script_id=2882)  
提供快速生成代码段的功能.  
[markdown](http://www.vim.org/scripts/script.php?script_id=2882)  
MarkDown语法高亮.  
[NERD_commenter](http://www.vim.org/scripts/script.php?script_id=1218)  
提供快速注释/反注释代码块的功能.  


