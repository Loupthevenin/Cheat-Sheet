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
