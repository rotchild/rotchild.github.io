# docker学习
[参考资料](http://imcjy.com/)<br/>
1. ## 安装
1. ## 使用阿里云docker镜像加速
``
sudo mkdir -p /etc/docker
sudo tee /etc/docker/daemon.json <<-'EOF'
{
  "registry-mirrors": ["https://******.mirror.aliyuncs.com"]
}
EOF
sudo systemctl daemon-reload
sudo systemctl restart docker
``
1. ## 拉取镜像
``
docker pull mysql
``
1. ## 创建容器
``
sudo docker run --name first-mysql -p 3306:3306 -e MYSQL\_ROOT\_PASSWORD=123456 -d mysql
``
前面的3306为本机的端口,后面的3306位mysql默认的端口<br/>
再创建mysql容器时,只要保证前面的不同即可<br/>
``
sudo docker run --name first-mysql -p 3307:3306 -e MYSQL\_ROOT\_PASSWORD=123456 -d mysql
``

1. ## 停止容器
``
docker stop 容器id
``

1. ## 进入docker容器的方法
[参考资料](https://www.cnblogs.com/xhyan/p/6593075.html)
* 使用docker exec进入Docker容器
``
sudo docker exec -it 775c7c9ee1e1 /bin/bash 
``
