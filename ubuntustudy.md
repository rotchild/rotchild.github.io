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
1. mkdir -p<br/>
   * 参数P代表parents，表示递归创建目录。
   * 如果用-p 可以直接创建2个目录 mkdir -p 目录A/子目录B就可以。
   
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
1. 要检查特定的包，比如firefox是否安装了，使用这个命令：
  ```
  dpkg -s firefox
  ```
1. 卸载指定软件
  ```
  sudo apt-get remove softname
  ```
  彻底卸载<br/>
   * 删除软件及其配置文件
  ```
  apt-get --purge remove <package>
  ```
   * 删除没用的依赖包
  ```
  apt-get autoremove <package>
  ```
   * 此时dpkg的列表中有“rc”状态的软件包，可以执行如下命令做最后清理
  ```
  dpkg -l |grep ^rc|awk '{print $2}' |sudo xargs dpkg -P
  ```
1. 安装指定软件
```
sudo apt-get install <package>
```
## 目录相关
1. pwd<br/>
   pwd 命令能让你知道你目前工作的目录是哪个目录
