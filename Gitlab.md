## gitlab简介
gitlab 是一个基于git实现的在线代码仓库软件,可以用gitlab自己搭建一个类似于github一样的系统，一般用于在企业、学校等内部网络搭建git私服
## 使用docker安装gitlab
[docker配置参考资料](http://imcjy.com/)
 * ## 拉取镜像
``
docker pull gitlab/gitlab-ce
``
* ## 创建并运行gitlab容器
``
sudo docker run --detach \
    --hostname 40.125.206.47 \
    --publish 443:443 --publish 80:80 --publish 8888:22 \
    --name gitlab \
    --restart always \
    --volume /srv/gitlab/config:/etc/gitlab \
    --volume /srv/gitlab/logs:/var/log/gitlab \
    --volume /srv/gitlab/data:/var/opt/gitlab \
    gitlab/gitlab-ce:latest
``
### 参数说明：
* --detach: 设置容器后台运行
* --hostname: 设置容器的 hostname
* --publish: 端口转发规则（80：Http 访问端口，443：Https 访问端口，8888：主机的 ssh 访问端口，22：Docker 容器中 ssh 访问端口）
* --name：容器名称
* --restart always：每次启动容器就重启GitLab
* --volume: 共享目录挂载，即 docker 容器内外数据共享（/srv/gitlab/data: 应用程序数据，/srv/gitlab/logs：GitLab 的 log，/srv/gitlab/config：GitLab 的配置文件）
* --e：配置 Gitlab 运行的环境变量

* ## 注意事项
      1.  项目的ip地址修改：<br/>
     进入到gitlab容器之后<br/>
     ``
      * cd /opt/gitlab/embedded/service/gitlab-rails/config
      * vim gitlab.yml  
     ``
     修改gitlab下host值为实际的域名或服务器IP地址即可，保存退出<br/>
     
     注意**使用docker重启容器无效,需要在容器中重启**<br/>[如何进入docker容器内](./docker.md)
     ``
     gitlab-ctl restart<br/>
     ``
     1.  push权限问题
      master 默认为proceted branch,权限级别为master,需要在Settings中的Repository中修改权限级别
