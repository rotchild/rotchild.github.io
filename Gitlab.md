# 使用docker安装gitlab
 ##  1. 拉取镜像
``
docker pull gitlab/gitlab-ce
``
## 1. 创建并运行gitlab容器
``
docker run --name='gitlab-ce' -d \
       --net=none \
       --restart always \
       --volume /home/gitlab/config:/etc/gitlab \
       --volume /home/gitlab/logs:/var/log/gitlab \
       --volume /home/gitlab/data:/var/opt/gitlab \
       gitlab/gitlab-ce
``
