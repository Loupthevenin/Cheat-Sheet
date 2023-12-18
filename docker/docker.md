# Docker

Documentation: [Docker Documentation](https://docs.docker.com/engine/)

## Index

---
- [**Requirements**](#requirements)
- [**Install Docker Engine Ubuntu**](#install-docker-engine-ubuntu)
    - [**Ubuntu**](#ubuntu)
    - [**Debian**](#debian)
    - [**Fast-install**]()
    - [**Post-installation**](#post-installation-steps)
- [**Docker CLI**](#cli)
    - [**Info**](#info)
    - [**Start and stop**](#start-and-stop)
    - [**Import/Export**](#import-/-export)
    - [**Images**](#images)
- [**Docker Compose**](#docker-compose)
- [**Tips CLI**](#tips)

## Requirements

- Ubuntu 23.10
- Ubuntu 23.04
- Ubuntu 22.04
- Ubuntu 20.04
- Debian 11
- Debian 12

## Install Docker Engine

### Ubuntu

Documentation: [Docker Install Ubuntu](https://docs.docker.com/engine/install/ubuntu/)

GPG key :

```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

Add repository to apt sources :

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/ubuntu \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

Install Docker packages :

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```


### Debian

Documentation: [Docker Install Ubuntu](https://docs.docker.com/engine/install/debian/)

GPG key :

```
sudo apt-get update
sudo apt-get install ca-certificates curl gnupg
sudo install -m 0755 -d /etc/apt/keyrings
curl -fsSL https://download.docker.com/linux/debian/gpg | sudo gpg --dearmor -o /etc/apt/keyrings/docker.gpg
sudo chmod a+r /etc/apt/keyrings/docker.gpg
```

Add repository to apt sources :

```
echo \
  "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.gpg] https://download.docker.com/linux/debian \
  $(. /etc/os-release && echo "$VERSION_CODENAME") stable" | \
  sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update
```

Install Docker packages :

```
sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin
```
### Fast-install

One click installation script:

```
curl -fsSL https://get.docker.com -o get-docker.sh
sudo sh get-docker.sh
```


### Post-installation steps

Documentation: [Docker post-installation](https://docs.docker.com/engine/install/linux-postinstall/)

```
sudo groupadd docker
sudo usermod -aG docker "user"
```

## CLI

Documentation: [Docker CLI](https://docs.docker.com/engine/reference/commandline/cli/)

### Info

- `docker ps` List containers running
- `docker ps -a` List ALL containers
- `docker logs` gets logs from container
- `docker inspect` all the info
- `docker port` shows port of container
- `docker top` shows running processes in container

### Start and stop

- `docker create` creates a container (not start)
- `docker rename` rename container
- `docker run` creates and starts a container
- `docker rm` deletes a container
- `docker update` update a container
- `docker start` start a container
- `docker stop` stop a container
- `docker restart` stop and starts a container
- `docker`

### Import / Export

- `docker cp` copies files
- `docker export` turns container into tarball

### Images

- `docker images` shows all images
- `docker import` creates an image from a tarball
- `docker build` creates image from Dockerfile
- `docker rmi` removes an image

Load/Save image

- `docker load < image.tar.gz`
- `docker save image:tag | gzip > image.tar.gz`

## Docker-Compose

Documentation: [Docker Compose](https://docs.docker.com/compose/)


- `docker-compose -f 'file.yaml' up`
- `docker-compose stop`

## Tips

Delete ALL containers

```
docker rm -f $(docker ps -qa)
```

Delete old containers

```
docker ps -a | grep 'weeks ago' | awk '{print$1} | xargs docker rm
```

Delete stopped containers

```
docker rm -v $(docker ps -a -q -f status=exited)
```

Delete all images

```
docker rmi $(docker images -q)
```
