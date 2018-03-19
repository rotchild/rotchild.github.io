# 使用docker安装gitlab
 ##  1. 拉取镜像
``
docker pull gitlab/gitlab-ce
``
## 1. 创建并运行gitlab容器
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
