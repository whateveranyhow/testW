# Beyond the Basic Stuff with Python

- - [Introduction](https://inventwithpython.com/beyond/chapter0.html)
  - [Chapter 1 - Dealing with Errors and Asking for Help](https://inventwithpython.com/beyond/chapter1.html)
  - [Chapter 2 - Environment Setup and the Command Line](https://inventwithpython.com/beyond/chapter2.html)
  - [Chapter 3 - Code Formatting with Black](https://inventwithpython.com/beyond/chapter3.html)
  - [Chapter 4 - Choosing Understandable Names](https://inventwithpython.com/beyond/chapter4.html)
  - [Chapter 5 - Finding Code Smells](https://inventwithpython.com/beyond/chapter5.html)
  - [Chapter 6 - Writing Pythonic Code](https://inventwithpython.com/beyond/chapter6.html)
  - [Chapter 7 - Programming Jargon](https://inventwithpython.com/beyond/chapter7.html)
  - [Chapter 8 - Common Python Gotchas](https://inventwithpython.com/beyond/chapter8.html)
  - [Chapter 9 - Esoteric Python Oddities](https://inventwithpython.com/beyond/chapter9.html)
  - [Chapter 10 - Writing Effective Functions](https://inventwithpython.com/beyond/chapter10.html)
  - [Chapter 11 - Comments, Docstrings, and Type Hints](https://inventwithpython.com/beyond/chapter11.html)
  - [Chapter 12 - Organizing Your Code Projects with Git](https://inventwithpython.com/beyond/chapter12.html)
  - [Chapter 13 - Measuring Performance and Big O Algorithm Analysis](https://inventwithpython.com/beyond/chapter13.html)
  - [Chapter 14 - Practice Projects](https://inventwithpython.com/beyond/chapter14.html)
  - [Chapter 15 - Object-Oriented Programming and Classes](https://inventwithpython.com/beyond/chapter15.html)
  - [Chapter 16 - Object-Oriented Programming and Inheritance](https://inventwithpython.com/beyond/chapter16.html)
  - [Chapter 17 - Pythonic OOP: Properties and Dunder Methods](https://inventwithpython.com/beyond/chapter17.html)





| C2   | C3   | C4   | C5   | C6   | C7   | C8   | C9   | C10  | C11  | C12  |
| ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- | ---- |
| 100  |      |      |      |      |      |      |      |      |      |      |



[TOC]

# C1 处理错误及请求帮助。

> **python “ZeroDivisionError: division by zero”**     #搜索时打引号

## 1. 三步处理错误：

1. Examining Tracebacks
2. Searching for Error Messages
3. Preventing Errors with Linters
4. 关于安装linter：

 You can install Pyflakes(一种a linter) from https://pypi.org/project/pyflakes/ or by running `pip install --user pyflakes`.

\*On Windows, you can run the* python *and* pip *commands. But on macOS and Linux, these command names are for Python version 2 only, so instead you’ll need to run* python3 *and* pip3\*

## 2. 请求帮助

* 官方引导： https://www.python.org/about/help/

* https://www.reddit.com/r/learnpython/

* 储存代码格式的网站 https://pastebin.com/

* 附上了一个好的问题格式。



# C2 环境设置和命令行

内容包括： 文件系统，路径，home目录（系统盘所在的位置），当前工作文件夹，绝对路径，相对路径，程序和进程； 命令行、打开终端窗口、输入命令行运行程序、命令行参数、-c参数来运行python、命令行运行python、运行py.exe.程序、用python模块subprocess运行shell commands、Tab快捷输入、查看命令行历史（W：doskey /history  ；咋不管用， `history` command）

##### * 常用命令行--可以查“Linux与Windows命令对比”

1. 通配符匹配文件夹和文件名，如dir *.py

2. 切换目录 cd 

   ​    * home文件夹：`cd ~` on macOS and Linux； `cd %USERPROFILE%` on Windows

   ​    * 文件夹有空格，要加双引号。

   ​    * windows切换盘 用 `d:`   ； 返回上一层  `cd ..`

3. 列出目录dir和ls

   ​      ls -al可以出现更多信息： Linux和macOS

4. 找文件

   ​     * windows: `dir /s *.py` 遍历父和子文件夹取找py文件

   ​     * 同样的命令： `find . -name  "*.py"` 注意后面打了引号。

5. 复制文件和文件夹

   ​    `copy  [source file or folder]  [destination folder]`

   ​     `cp` `[source file or folder] [destination folder]`

6. 移动文件和文件夹

   ​    `move [source file or folder] [destination folder]`

   ​    `mv[source file or folder]``[destination folder]` 

7. 使用ren and mv重命名

   ​	`ren[file or folder] [new name]`

   ​     `mv[file or folder] [new name]` 

8. 删除文件

   ​	`del[file or folder]` #只删除文件，不删除文件名，不影响子文件夹，

   ​	`del /s /q [file or folder]` 安静地删除所有文件，包含子文件夹里的文件，非文件夹。

   ​	`rm[file]`

   ​	`rd /s /q [folder]` #删除windows整个文件夹

   ​	`rm –r[folder]` #删除linus/macOS整个文件夹

9. 新建文件夹

   ​	`md[new folder]`

10. 删除文件夹

    ​	`rd[source folder]`： widnows

    ​	`rmdir[source folder]`: macOS and Linux

11. 找程序的目录

    ​	`where `[program] on Windows ；不知道为什么， 我这个只能用powershell输入gcm查询

    ​    `which `[program] on macOS and Linux 

12. 清空终端窗口

    ​	`cls` on Windows 

    ​     `clear` on macOS

    

##### 	* 环境变量和路径

1. 查看环境变量

   `set` (on Windows) or `env` (on macOS and Linux) 

   查看home环境变量

   `echo` command. Run `echo %HOMEPATH%` on Windows or `echo $HOME` on macOS and Linux 

   > 环境变量的顺序有先后

2. 临时变更环境变量

   `path C:\newFolder;%PATH%`

   `PATH=/newFolder:$PATH`

3. 永久变更环境变量

   `setx /M PATH "C:\newFolder;%PATH%"`

   `export PATH=/newFolder:$PATH`

4. 方便运行python的方法

   windows:以下文件保存为.bat。

   ```
   @py.exe C:\path\to\yourScript.py %*
   @pause
   ```

   linux需要保存到home文件夹中，.py文件首行写`#!/usr/bin/env python3`(*shebang line*)，输入`./yourScript.py` 运行。

   ```
   chmod u+x yourScript.py
   ```

   

   





 



