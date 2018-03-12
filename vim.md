# Vim 的基本概念
基本上vi可以分为三种状态，分别是命令模式（command mode）、插入模式（Insert mode）和底行模式（last line mode），各模式的功能区分如下：
1.  **命令行模式command mode）**<br/>
控制屏幕光标的移动，字符、字或行的删除，移动复制某区段及进入Insert mode下，或者到 last line mode。
1.  **插入模式（Insert mode）**<br/>
只有在Insert mode下，才可以做文字输入，按「ESC」键可回到命令行模式。
1.  **底行模式（last line mode）**<br/>
将文件保存或退出vi，也可以设置编辑环境，如寻找字符串、列出行号……等。<br/>
不过一般我们在使用时把vi简化成两个模式，就是将底行模式（last line mode）也算入命令行模式command mode）

# Vim 的基本操作
1. 进入vi之后，是处于「命令行模式（command mode）,`在「命令行模式（command mode）」下按一下字母「i」`就可以进入「插入模式（Insert mode）」
1. 处于「插入模式（Insert mode）」，您就只能一直输入文字，如果您发现输错了字！`想用光标键往回移动，将该字删除，就要先按一下「ESC」键转到「命令行模式（command mode）」再删除文字。`
1. 在「命令行模式（command mode）」下，按一下「：」冒号键进入「Last line mode」，例如：
   1.  : w filename （输入 「w filename」将文章以指定的文件名filename保存）
   1.  : wq (输入「wq」，存盘并退出vi)
   1.  : q! (输入q!， 不存盘强制退出vi)
