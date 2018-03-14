# Ubuntu 命令List

## 文件操作
1. mkdir-p:no error if existing, make parent directories as needed
1. chown jim program.c<br/>文件 program.c 的所有者更改为 jim。作为所有者，jim 可以使用 chmod 命令允许或拒绝其他用户访问 program.c。
1. chown -R john:build /tmp/src更改目录的所有者：将目录 /tmp/src 中所有文件的所有者和组更改为用户 john 和组 build<br/>- R 递归式地改变指定目录及其下的所有子目录和文件的拥有者。
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
   x，y，z的值由r（r=4），w ( w=2 )，x ( x=1 )来确定<br/>
   chmod 755 /home/gitadmin/respoitories :表示User(4+2+1) 拥有读、写、运行权限,Group(4+1)拥有读、运行权限,Other(4+1)拥有读、运行权限
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
1. cd<br/>
   目录名有几个符号有特殊的含义，“..”代表上一级目录、“~”代表HOME目录、“-”代表前一目录。
1. rm [选项] 文件<br/>
   删除文件<br/>
  -f, --force          强力删除，不要求确认<br/>
  -i                       每删除一个文件或进入一个子目录都要求确认<br/>
  -I                       在删除超过三个文件或者递归删除前要求确认<br/>
  -r, -R                递归删除子目录**删除文件夹时使用**<br/>
  -d, --dir             删除空目录<br/>
  -v, --verbose     显示删除结果<br/>
1. ls -l filename<br/>
   查看文件操作权限
1. cat主要有三大功能:[参考点这里](http://blog.csdn.net/jackalfly/article/details/7556848)
   1. 一次显示整个文件。
$ cat   filename
   1. 从键盘创建一个文件。
$ cat  >  filename
只能创建新文件,不能编辑已有文件.
   1. 将几个文件合并为一个文件。
$cat   file1   file2  > file
1. touch a.txt
创建文件
1. mv 移动文件，修改文件名
mv 源文件 目标文件 例如mv a.txt b.txt 是在将当前目录下的a.txt文件名字改为b.txt<br/>
mv 源文件 目录,例如mv a.txt /home 是将a.txt文件移动到/home目录下

1.cd cd带空格的目录,将目录用引号括起来

1. 重定向
重定向分为**输入重定向**与**输出重定向**。
所谓的输入重定向``即输入不从键盘读入，而是从文件输入或其它``。<br/>
所谓的输出重定向``即不输出到终端上，而是输出到文件中去或其它``。<br/>
""<"表示输入重定向运算符,">"表示输出重定向t运算符。<br/>
"<<"这种输入告诉Shell，当前标准输入来自命令行的一对分隔号的中间内容。<br/>
">>",用">"输出时，如果文件不存在会自动建立一个文件，如果第二次输入时，会覆盖前一次的输入内容，而">>"表示把第二次的输出内容追加到文件中去，而不是覆盖。<br/>
## 安装包操作
1. 要检查特定的包，比如firefox是否安装了，使用这个命令：
  ```
  dpkg -s firefox
  ```
  或<br/>
  ```
  dpkg-query -l <package>
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
1. 查看软件是否在运行
```
ps -ef|grep <package>如果有内容说明活着 
```
[ps点这里](https://www.cnblogs.com/wxgblogs/p/6591980.html)
## 目录相关
1. pwd<br/>
   pwd 命令能让你知道你目前工作的目录是哪个目录
   
## 账户相关
1.切换账户:<br/>
  切换用户的命令为：su username<br/>
  在切换用户时，如果想在切换用户之后使用新用户的工作环境，可以在su和username之间加- :su -username<br/>
  从普通用户切换到root用户，还可以使用命令：sudo su<br/>
  在终端输入exit或logout或使用快捷方式ctrl+d，可以退回到原来用户，其实ctrl+d也是执行的exit命令<br/>
  
## 服务相关
1. 开启服务：<br/>
service <servicename> start
1. 重启服务：<br/>
service <servicename> restart
1. 查看某个服务的状态:<br/>
service <servicename> status
1. 停止某个服务:<br/>
service <servicename> stop

# sftp使用
sftp user@host
[sftp详情](http://blog.csdn.net/stpeace/article/details/39404449)

# 网络部分
curl<br/>
curl命令是个功能强大的网络工具，支持通过http、ftp等方式下载文件、上传文件。还可以用来抓取网页、网络监控等方面的开发，解决开发过程中遇到的问题。
[详情点这里](https://www.cnblogs.com/linjiqin/p/5484910.html)
