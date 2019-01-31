## 配置

编辑`Dockerfile`，一些写法可以参考已有镜像。

```
# 单独载入docker镜像
$ docker build -t docker-fe:v1  .
$ docker images
# <none>              <none>              5f6d76aefc46        33 seconds ago      298MB
# 运行容器 
$ docker run --rm -itd  -p 9528:8080 -v ~/x/docker-demos/samples/Dockerfile-fe/nodejs:/workspace --name dockerfile-fe --restart=always 5f6d76aefc46
$ docker container ls --all
# 8729e06b1d37        5f6d76aefc46        "node"                   10 seconds ago      Up 9 seconds               0.0.0.0:9528->8080/tcp   dockerfile-fe
$ docker exec -it dockerfile-fe /bin/zsh
$ docker rmi 5f6d76aefc46 -f
$ docker build -t docker-fe:v0.0.1  .
# <none>              <none>              aaa4f95e37cb        13 minutes ago      298MB  #
# 处理相关报错。直到输出Successfully
# 修改名字
$ docker tag fe huixisheng/fe:v1
```

`/bin/sh: 1: cannot create /root/.oh-my-zsh/custom/custom.zsh: Directory nonexistent` 导致创建`image`为<none>

```
npm WARN deprecated cross-spawn-async@2.2.5: cross-spawn no longer requires a build toolchain, use it instead
npm WARN deprecated socks@1.1.10: If using 2.x branch, please upgrade to at least 2.1.6 to avoid a serious bug with socket data flow and an import issue introduced in 2.1.0
npm WARN deprecated browserslist@1.7.7: Browserslist 2 could fail on reading Browserslist >3.0 config used in other tools.
```

```
debconf: delaying package configuration, since apt-utils is not installed
```
[出现 debconf: delaying package configuration, sin... - 简书](https://www.jianshu.com/p/99fd61e6aa29)

```
W: GPG error: http://dl.yarnpkg.com stable InRelease: The following signatures couldn't be verified because the public key is not available: NO_PUBKEY 23E7166788B63E1E
```
`curl -sS https://dl.yarnpkg.com/debian/pubkey.gpg | sudo apt-key add -`
- [GPG error: https://dl.yarnpkg.com/debian stable InRelease NO_PUBKEY E074D16EB6FF4DE3 · Issue #4453 · yarnpkg/yarn](https://github.com/yarnpkg/yarn/issues/4453)
- [The following signatures couldn't be verified because the public key is not available: NO_PUBKEY E074D16EB6FF4DE3 · Issue #4505 · yarnpkg/yarn](https://github.com/yarnpkg/yarn/issues/4505)

```
docker push denied: requested access to the resource is denied
```
上传自己的镜像被拒绝denied: requested access to the resource is denied - 关于代码的那点事儿... - CSDN博客 https://blog.csdn.net/wzygis/article/details/78205867

## 创建镜像方法 ##
1. 使用`docker commit`命令
2. 使用`docker build`命令和`Dockerfile`文件