# Requirements

## Hardware

CPU x86_64, 4Gb memory+, 10Gb+ free disk space.

## OS

Linux. x86_64 only. CentOS 7.

## Software

* `git`, `docker`, `docker-compose`

## Install

* Install basic CentOS 7
* Install updates
* Install git

```
# yum install git
```

* Install docker requirements:

```
# yum install yum-utils device-mapper-persistent-data lvm2
```

* Enable external docker repository:

```
# yum-config-manager --add-repo https://download.docker.com/linux/centos/docker-ce.repo
# yum upgrade
```

* Install docker:

```
# yum install docker-ce docker-ce-cli containerd.io
```

* Enable and start docker:

```
# systemctl enable docker
# systemctl start docker
```

* Install docker-compose:

```
# curl -L "https://github.com/docker/compose/releases/download/1.24.0/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
# chmod +x /usr/local/bin/docker-compose
# ln -s /usr/local/bin/docker-compose /usr/bin/docker-compose
```

* Check that everything installed and worked right:

```
# git --version
git version 1.8.3.1
#
```

```
# docker --version
Docker version 18.09.5, build e8ff056
# docker-compose --version
docker-compose version 1.24.0, build 0aa59064
#
```

```
# docker run hello-world

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

#
```

Ok. Looks like everything installed and worked properly.
