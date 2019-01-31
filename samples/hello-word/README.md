## 相关命令 ##
```
$ docker image pull library/hello-world
$ docker image ls
$ docker container run hello-world
# # 列出本机所有容器，包括终止运行的容器
$ docker container ls --all
```

```
REPOSITORY             TAG                 IMAGE ID            CREATED             SIZE
<none>                 <none>              be03ca98e604        20 hours ago        182MB
hello-world            latest              fce289e99eb9        4 weeks ago         1.84kB
node                   8.11.3-slim         1d5555ef5229        6 months ago        182MB
```

```
Hello from Docker!
This message shows that your installation appears to be working correctly.

To generate this message, Docker took the following steps:
 1. The Docker client contacted the Docker daemon.
 2. The Docker daemon pulled the "hello-world" image from the Docker Hub.
    (amd64)
 3. The Docker daemon created a new container from that image which runs the
    executable that produces the output you are currently reading.
 4. The Docker daemon streamed that output to the Docker client, which sent it
    to your terminal.

To try something more ambitious, you can run an Ubuntu container with:
 $ docker run -it ubuntu bash

Share images, automate workflows, and more with a free Docker ID:
 https://hub.docker.com/

For more examples and ideas, visit:
 https://docs.docker.com/get-started/
```
输出了 `Hello from Docker!` 自动终止了