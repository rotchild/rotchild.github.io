## git概述
Git是一个免费的开源分布式版本控制系统，旨在处理速度和效率从小到大的项目<br/>
### git的特点
[参考资料](https://www.zhihu.com/question/20093241)
1. **分布式**：Git是没有中心服务器的，每个人机器上都是一个完整的库，我们平时开发代码时的中央服务器其实和我们自己机器上的库内容是完全一样的（格式有点不同，是bare的）
1. **本地提交**：Git拥有本地库
## git使用
[参考资料](https://www.liaoxuefeng.com/wiki/0013739516305929606dd18361248578c67b8067c8c017b000/00137396287703354d8c6c01c904c7d9ff056ae23da865a000)<br/>
 *  git用户配置<br/>

``
  git config --global user.name "Your Name"<br/>
  git config --global user.email "email@example.com"
``

 * clone远程库<br/>
``
git clone url
``

 * 添加文件<br/>
``
git add .
``

 * 查看状态<br/>
``
git status
``

 * 提交到本地仓库<br/>
``
git commit -m 备注 
``

* 提交到远程仓库<br/>
``
git push origin 分支名称
``
