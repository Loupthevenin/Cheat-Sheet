# Kubernetes

Documentation: [Kubernetes Documentation](https://kubernetes.io/docs/home/)

## Index

---
- [**Install kubectl**](#install-kubectl-binary-on-linux)
- [**Install Kubernetes**](#install-kubernetes)


## Install kubectl binary on Linux

Install binary :

```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl"
```

Validate binary :
```
curl -LO "https://dl.k8s.io/release/$(curl -L -s https://dl.k8s.io/release/stable.txt)/bin/linux/amd64/kubectl.sha256"
```

```
echo "$(cat kubectl.sha256)  kubectl" | sha256sum --check
```

Install kubectl :

```
sudo install -o root -g root -m 0755 kubectl /usr/local/bin/kubectl
```

## Install Kubernetes


- **NEED DOCKER**


Update apt :

```
sudo apt-get update
sudo apt-get install -y apt-transport-https ca-certificates curl gpg
```

DL public signing key :

```
curl -fsSL https://pkgs.k8s.io/core:/stable:/v1.28/deb/Release.key | sudo gpg --dearmor -o /etc/apt/keyrings/kubernetes-apt-keyring.gpg
```

Add the appropriate Kubernetes apt repository :

```
echo 'deb [signed-by=/etc/apt/keyrings/kubernetes-apt-keyring.gpg] https://pkgs.k8s.io/core:/stable:/v1.28/deb/ /' | sudo tee /etc/apt/sources.list.d/kubernetes.list
```
Update apt and install :

```
sudo apt-get update
sudo apt-get install -y kubelet kubeadm kubectl
sudo apt-mark hold kubelet kubeadm kubectl
```

