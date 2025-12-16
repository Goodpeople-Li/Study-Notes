# Docker常用命令
1. 下载镜像
   ```bash
   docker pull <镜像名称>:<标签>
   ```
   例如，下载最新的Ubuntu镜像：
   ```bash
   docker pull docker.io/library/ubuntu:latest
   ```
   docker.io是Docker Hub的官方仓库，library是命名空间。

2. 查看本地镜像
   ```bash
    docker images
    ```

3. 删除镜像
    ```bash
    docker rmi <镜像ID或名称>
    ```
    注：删除容器是docker rm
4. 运行容器
    ```bash
    docker run -it --name <容器名称> <镜像名称>:<标签> /bin/bash
    ```
    例如，运行一个Ubuntu容器：
    ```bash
    docker run -it --name my_ubuntu_container docker.io/library/ubuntu:latest /bin/bash
    ```
    注：docker run -d 表示后台运行容器，-it表示交互式终端。

5. 查看正在运行的容器
    ```bash
    docker ps
    ```

## 挂载卷
1. 运行容器时挂载主机目录到容器
   ```bash
   docker run -it -v /path/on/host:/path/in/container --name <容器名称> <镜像名称>:<标签> /bin/bash
   ```
   例如，将主机的`/home/user/data`目录挂载到容器的`/data`目录：
   ```bash
   docker run -it -v /home/user/data:/data --name my_ubuntu_container docker.io/library/ubuntu:latest /bin/bash
   ```

2. 绑定宿主机的端口到容器
   ```bash
   docker run -it -p <宿主机端口>:<容器端口> --name <容器名称> <镜像名称>:<标签> /bin/bash
   ```
   例如，将宿主机的8080端口绑定到容器的80端口：
   ```bash
   docker run -it -p 8080:80 --name my_web_container docker.io/library/ubuntu:latest /bin/bash
   ```

## 容器管理
1. 停止容器
   ```bash
   docker stop <容器ID或名称>
   ```
2. 启动容器
   ```bash
    docker start <容器ID或名称>
    ```
3. 重启容器
   ```bash
    docker restart <容器ID或名称>
    ```
4. 删除容器
    ```bash
     docker rm <容器ID或名称>
     ```
5. 查看所有容器（包括未运行的）
    ```bash
    docker ps -a
    ```
6. 查看当前容器的信息
    ```bash
    docker inspect <容器ID或名称>
    ```