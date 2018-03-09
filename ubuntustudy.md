# Ubuntu 命令List

## 文件操作
1. mkdir-p:no error if existing, make parent directories as needed
1. chown jim program.c<br/>文件 program.c 的所有者更改为 jim。作为所有者，jim 可以使用 chmod 命令允许或拒绝其他用户访问 program.c。
1. chmod 命令可以用来修改文件或文件夹的读写权限 <br/>chmod [ u / g / o / a ] [ + / - / = ] [ r / w / x ] file<br/>
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
