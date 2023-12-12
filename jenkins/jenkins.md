# Jenkins

Documentation: [Jenkins Documentation](https://www.jenkins.io/doc/book/installing/)

## Index

---
- [**Requirements**](#requirements)
- [**Install Java**](#install-java)
- [**Install Jenkins**](#install-jenkins)
    - [**Linux**](#linux)
    - [**Docker**]()
    - [**Kubernetes**]()

## Requirements

- **JAVA**

## Install Java

Install java :
```
sudo apt update
sudo apt install fontconfig openjdk-17-jre
```
Validate install : 

```
java -version
```

## Install Jenkins

### Linux

Install Jenkins Debian/Ubuntu :
```
sudo wget -O /usr/share/keyrings/jenkins-keyring.asc \
  https://pkg.jenkins.io/debian-stable/jenkins.io-2023.key
echo "deb [signed-by=/usr/share/keyrings/jenkins-keyring.asc] \
  https://pkg.jenkins.io/debian-stable binary/" | sudo tee \
  /etc/apt/sources.list.d/jenkins.list > /dev/null
sudo apt-get update
sudo apt-get install jenkins
```

### Docker

```

```

