# 搭建git服务器的步骤

## git服务器环境
Ubutu 16.04 LTS

## 搭建步骤
* 安装git,设置仓库目录和访问权限<br/>
``
  * sudo apt-get install git git-clore --安装git服务器
  * sudo mkdir/home/gitadmin/repositories --创建git仓库目录
  * sudo chown gitadmin:gitadmin/home/gitadmin/respositories --设定所有者
  * sudo chmod 755 /home/gitadmin/repositories --设置仓库的访问权限
``
* 配置ssh服务<br/>
``
sudo apt-get install openssh-server
sudo vim/etc/ssh/sshd_config 
找到如下几行，去掉"#"
StrictModes no --在用户名和其公钥不匹配的时候通过认证
RSAAuthentication yes --使用纯的RSA验证
PubkeyAuthentication yes --允许Public key AuthorizedKeysFile %h/.ssh/authorized_keys
上面这个配置是设定免密码登录的账号公钥存储路径
``

* PC 端 安装git
 在 git.bash下
``
ssh-keygen -t rsa 生成本机密钥,公钥默认在~/.ssh/id_rsa.pub
``
