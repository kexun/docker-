# docker-learning

#####docker命令
获取镜像：docker pull ubuntu  

查看本地已有镜像：docker images  

替换标签：docker tag ubuntu:14.04 newname:newname  

查看镜像详情：docker inspect <imaeg id>  

在默认docker hub搜索镜像：docker search TERM  

删除镜像：docker rmi <image id>  

如果进行正在运行 无法删除，则需要先删除运行的容器，先查找当前运行的容器：docker ps -a  

删除当前容器：docker rm <容器id>  

根据当前容器创建镜像：docker commit -m "comment message" -a "aaa message" dfd234f94218 test  

存出镜像：docker save -o test.tar test  

载入镜像：docker load --unput test.tar  