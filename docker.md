# docker学习
[参考资料](http://imcjy.com/)<br/>
1.  ## 安装
1. ## 拉取镜像
``
docker pull mysql
``
1. ## 创建容器
``
sudo docker run --name first-mysql -p 3306:3306 -e MYSQL\_ROOT\_PASSWORD=123456 -d mysql
``
1. 停止容器
``
docker stop 容器id
``
