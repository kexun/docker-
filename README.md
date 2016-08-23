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

#####容器操作命令

创建容器：docker create -it ubuntu:14.04 该方法创建以后容器是停止的，除非加上参数 -d 后台运行  

启动容器：docker start <container id>  

终止容器：docker stop <container id>  

重启容器：docker restart <container id>  

进入容器：docker attach <container id>  

nsenter命令：用attach命令进入容器有一个缺点，就是多个终端同时attach了同一个容器以后，所以终端的显示会一致，并且当exit以后，容器就会停止。 因此要使用nsenter工具。各个终端可以独立操作，并且退出的时候不会停止容器。  
nsenter --target 6607 --mount --uts --ipc --net --pid  

导出容器：docker export 576 > test.tar  
之前有一个save的命令，这是存出镜像操作，略有区别。save是保存镜像到本地文件，保存的数据比较全面。export是保存当前容器的快照到本地文件，他会丢失所有的历史数据以及元数据，因此体积会比之前小一点。  

导入容器：cat test.tar | docker import - test/ubuntu:v2  
这个命令和load对应，load是导入一个镜像，而import是导入一个容器的快照。  


















