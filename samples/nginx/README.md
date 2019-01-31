## 安装 ##

### 查找 ###

<details>
    <summary>`docker search nginx`</summary>
    <p>
```
NAME                                                   DESCRIPTION                                     STARS               OFFICIAL            AUTOMATED
nginx                                                  Official build of Nginx.                        10804               [OK]
jwilder/nginx-proxy                                    Automated Nginx reverse proxy for docker con…   1514                                    [OK]
richarvey/nginx-php-fpm                                Container running Nginx + PHP-FPM capable of…   678                                     [OK]
jrcs/letsencrypt-nginx-proxy-companion                 LetsEncrypt container to use with nginx as p…   473                                     [OK]
webdevops/php-nginx                                    Nginx with PHP-FPM                              122                                     [OK]
kitematic/hello-world-nginx                            A light-weight nginx container that demonstr…   119
zabbix/zabbix-web-nginx-mysql                          Zabbix frontend based on Nginx web-server wi…   86                                      [OK]
bitnami/nginx                                          Bitnami nginx Docker Image                      60                                      [OK]
linuxserver/nginx                                      An Nginx container, brought to you by LinuxS…   53
1and1internet/ubuntu-16-nginx-php-phpmyadmin-mysql-5   ubuntu-16-nginx-php-phpmyadmin-mysql-5          48                                      [OK]
zabbix/zabbix-web-nginx-pgsql                          Zabbix frontend based on Nginx with PostgreS…   28                                      [OK]
tobi312/rpi-nginx                                      NGINX on Raspberry Pi / armhf                   24                                      [OK]
nginx/nginx-ingress                                    NGINX Ingress Controller for Kubernetes         15
blacklabelops/nginx                                    Dockerized Nginx Reverse Proxy Server.          12                                      [OK]
wodby/drupal-nginx                                     Nginx for Drupal container image                11                                      [OK]
centos/nginx-18-centos7                                Platform for running nginx 1.8 or building n…   10
nginxdemos/hello                                       NGINX webserver that serves a simple page co…   10                                      [OK]
centos/nginx-112-centos7                               Platform for running nginx 1.12 or building …   6
1science/nginx                                         Nginx Docker images that include Consul Temp…   4                                       [OK]
pebbletech/nginx-proxy                                 nginx-proxy sets up a container running ngin…   2                                       [OK]
travix/nginx                                           NGinx reverse proxy                             2                                       [OK]
mailu/nginx                                            Mailu nginx frontend                            2                                       [OK]
toccoag/openshift-nginx                                Nginx reverse proxy for Nice running on same…   1                                       [OK]
ansibleplaybookbundle/nginx-apb                        An APB to deploy NGINX                          0                                       [OK]
wodby/nginx                                            Generic nginx                                   0                                       [OK]
```
    </p>
</details>


<details>
    <summary>docker run --help</summary>
    <content>
```
Usage:  docker run [OPTIONS] IMAGE [COMMAND] [ARG...]

Run a command in a new container

Options:
      --add-host list                  Add a custom host-to-IP mapping (host:ip)
  -a, --attach list                    Attach to STDIN, STDOUT or STDERR
      --blkio-weight uint16            Block IO (relative weight), between 10 and 1000, or 0 to disable (default 0)
      --blkio-weight-device list       Block IO weight (relative device weight) (default [])
      --cap-add list                   Add Linux capabilities
      --cap-drop list                  Drop Linux capabilities
      --cgroup-parent string           Optional parent cgroup for the container
      --cidfile string                 Write the container ID to the file
      --cpu-period int                 Limit CPU CFS (Completely Fair Scheduler) period
      --cpu-quota int                  Limit CPU CFS (Completely Fair Scheduler) quota
      --cpu-rt-period int              Limit CPU real-time period in microseconds
      --cpu-rt-runtime int             Limit CPU real-time runtime in microseconds
  -c, --cpu-shares int                 CPU shares (relative weight)
      --cpus decimal                   Number of CPUs
      --cpuset-cpus string             CPUs in which to allow execution (0-3, 0,1)
      --cpuset-mems string             MEMs in which to allow execution (0-3, 0,1)
  -d, --detach                         Run container in background and print container ID
      --detach-keys string             Override the key sequence for detaching a container
      --device list                    Add a host device to the container
      --device-cgroup-rule list        Add a rule to the cgroup allowed devices list
      --device-read-bps list           Limit read rate (bytes per second) from a device (default [])
      --device-read-iops list          Limit read rate (IO per second) from a device (default [])
      --device-write-bps list          Limit write rate (bytes per second) to a device (default [])
      --device-write-iops list         Limit write rate (IO per second) to a device (default [])
      --disable-content-trust          Skip image verification (default true)
      --dns list                       Set custom DNS servers
      --dns-option list                Set DNS options
      --dns-search list                Set custom DNS search domains
      --entrypoint string              Overwrite the default ENTRYPOINT of the image
  -e, --env list                       Set environment variables
      --env-file list                  Read in a file of environment variables
      --expose list                    Expose a port or a range of ports
      --group-add list                 Add additional groups to join
      --health-cmd string              Command to run to check health
      --health-interval duration       Time between running the check (ms|s|m|h) (default 0s)
      --health-retries int             Consecutive failures needed to report unhealthy
      --health-start-period duration   Start period for the container to initialize before starting health-retries countdown (ms|s|m|h) (default 0s)
      --health-timeout duration        Maximum time to allow one check to run (ms|s|m|h) (default 0s)
      --help                           Print usage
  -h, --hostname string                Container host name
      --init                           Run an init inside the container that forwards signals and reaps processes
  -i, --interactive                    Keep STDIN open even if not attached
      --ip string                      IPv4 address (e.g., 172.30.100.104)
      --ip6 string                     IPv6 address (e.g., 2001:db8::33)
      --ipc string                     IPC mode to use
      --isolation string               Container isolation technology
      --kernel-memory bytes            Kernel memory limit
  -l, --label list                     Set meta data on a container
      --label-file list                Read in a line delimited file of labels
      --link list                      Add link to another container
      --link-local-ip list             Container IPv4/IPv6 link-local addresses
      --log-driver string              Logging driver for the container
      --log-opt list                   Log driver options
      --mac-address string             Container MAC address (e.g., 92:d0:c6:0a:29:33)
  -m, --memory bytes                   Memory limit
      --memory-reservation bytes       Memory soft limit
      --memory-swap bytes              Swap limit equal to memory plus swap: '-1' to enable unlimited swap
      --memory-swappiness int          Tune container memory swappiness (0 to 100) (default -1)
      --mount mount                    Attach a filesystem mount to the container
      --name string                    Assign a name to the container
      --network string                 Connect a container to a network (default "default")
      --network-alias list             Add network-scoped alias for the container
      --no-healthcheck                 Disable any container-specified HEALTHCHECK
      --oom-kill-disable               Disable OOM Killer
      --oom-score-adj int              Tune host's OOM preferences (-1000 to 1000)
      --pid string                     PID namespace to use
      --pids-limit int                 Tune container pids limit (set -1 for unlimited)
      --privileged                     Give extended privileges to this container
  -p, --publish list                   Publish a container's port(s) to the host
  -P, --publish-all                    Publish all exposed ports to random ports
      --read-only                      Mount the container's root filesystem as read only
      --restart string                 Restart policy to apply when a container exits (default "no")
      --rm                             Automatically remove the container when it exits
      --runtime string                 Runtime to use for this container
      --security-opt list              Security Options
      --shm-size bytes                 Size of /dev/shm
      --sig-proxy                      Proxy received signals to the process (default true)
      --stop-signal string             Signal to stop a container (default "SIGTERM")
      --stop-timeout int               Timeout (in seconds) to stop a container
      --storage-opt list               Storage driver options for the container
      --sysctl map                     Sysctl options (default map[])
      --tmpfs list                     Mount a tmpfs directory
  -t, --tty                            Allocate a pseudo-TTY
      --ulimit ulimit                  Ulimit options (default [])
  -u, --user string                    Username or UID (format: <name|uid>[:<group|gid>])
      --userns string                  User namespace to use
      --uts string                     UTS namespace to use
  -v, --volume list                    Bind mount a volume
      --volume-driver string           Optional volume driver for the container
      --volumes-from list              Mount volumes from the specified container(s)
  -w, --workdir string                 Working directory inside the container
```        
    </content>
</details>

```
# 下载
$ docker pull nginx
$ docker images
# 启动容器 #
$ docker run --help
$ docker run --name docker-samples-nginx --detach --publish 8080:80 nginx
# 可以看到启动的容器
$ docker container ls --all
# 进入容器， /bin/bash 不加不行
$ docker exec -it e48279c7bfe0 /bin/bash
# Attach local standard input, output, and error streams to a running container
$ docker attach e48279c7bfe0
```

```
docker run --rm -d --name docker-samples-nginx  \
  -p 8080:80 \
  -v ~/x/docker-demos/samples/nginx/html:/usr/share/nginx/html \
  -d \
  nginx
```

已存在`container name "/docker-samples-nginx"`，需要移除 `docker rm e48279c7bfe0d428dc84669a6cda360e2891dabdc86550dfdae0b836878d1673`

通过`http://0.0.0.0:8080/`访问。进入容器发现vi、ps等命令不能使用。nginx配置目录`/etc/nginx/`，root `/usr/share/nginx/html`。

### 安装vi ###
```
$ apt-get update
$ apt-get install vim
```

### 查看容器大小 ###
```
$ docker system df
```

### 查看容器ip ###
```
$ docker inspect <container id>
$ docker inspect --format='{{.Name}} - {{range .NetworkSettings.Networks}}{{.IPAddress}}{{end}}' $(docker ps -aq)
$ docker inspect -f '{{.Name}} - {{.NetworkSettings.IPAddress }}' $(docker ps -aq) 
```
[如何获取 docker 容器(container)的 ip 地址 - sannerlittle的博客 - CSDN博客](https://blog.csdn.net/sannerlittle/article/details/77063800)

## 参考 
docker-tutorial/nginx.md at master · jaywcjlove/docker-tutorial https://github.com/jaywcjlove/docker-tutorial/blob/master/docker/nginx.md