### 启动
#### 指定运行环境
正式环境：添加参数--spring.cloud.bootstrap.name=bootstrap-prod 
测试环境：添加参数--spring.cloud.bootstrap.name=bootstrap-dev

#### 部署
1. 编译打包后，运行docker文件夹下的./copy.sh，将文件复制到docker文件夹的目录中。

2. 上传docker文件夹到Linux服务器。

3. 在docker-compose.yml所在目录，运行指令。
3.1 例子：
docker-compose -f docker-compose.yml up -d ruoyi-mysql ruoyi-redis ruoyi-nacos ruoyi-minio
docker-compose -f docker-compose.yml up -d ruoyi-gateway ruoyi-nginx ruoyi-auth ruoyi-modules-system
3.2 如需重新部署容器:
docker stop ruoyi-gateway ruoyi-nginx ruoyi-auth ruoyi-modules-system
docker rm ruoyi-gateway ruoyi-nginx ruoyi-auth ruoyi-modules-system
docker rmi docker_ruoyi-gateway docker_ruoyi-auth docker_ruoyi-modules-system
3.3 更改运行参数:
在每个jar包中的dockerfile中更改