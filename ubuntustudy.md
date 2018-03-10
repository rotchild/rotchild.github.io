# Ubuntu 命令List

## 文件操作
1. mkdir-p:no error if existing, make parent directories as needed
1. chown jim program.c<br/>文件 program.c 的所有者更改为 jim。作为所有者，jim 可以使用 chmod 命令允许或拒绝其他用户访问 program.c。
1. chmod 命令可以用来修改文件或文件夹的读写权限 <br/>
   1. chmod [ u / g / o / a ] [ + / - / = ] [ r / w / x ] file<br/>
   ---------------------------------
   * u表示User，是文件的所有者
   * g表示跟User同Group的用户
   * o表示Other，即其他用户
   * a表示ALL，所有用户
   ---------------------------------
   * +表示增加权限
   * -表示取消权限
   * =表示取消之前的权限，并给予唯一的权限
   ----------------------------------
   * r表示Read，即读文件
   * w表示Write，即写文件
   * x表示运行文件
   2. chmod [xyz] file
   其中，x，y，z分别表示数字（最大不超过7），并分别对应User、Group、Other
   x，y，z的值由r（r=4），w ( w=2 )，x ( x=1 )来确定
   
1. ls -l 命令<br/>
   展示结果大体分为七列:<br/>
     1. 第一列 ： “drwxr-x---”  表识文件的类型 和文件权限  
     1. 第二列： “2”是纯数字 ，表示 文件链接个数 
     1. 第三列 ： “root” 表示文件的所有者 
     1. 第四列：“adm” 表示为文件的所在群组 
     1. 第五列：“4096”，表示为文件长度（大小）
     1. 第六列：“2013-08-07 11:03”，表示文件最后更新（修改）时间  
     1. 第七列：“apache2” 表示文件的名称  


## 安装包操作
1.要检查特定的包，比如firefox是否安装了，使用这个命令：<br/>
   dpkg -s firefox

## 目录相关
1. pwd<br/>
   pwd 命令能让你知道你目前工作的目录是哪个目录
