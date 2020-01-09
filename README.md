# docker
## docker installation on deepin
### deepin 15.11 upgrade docker-ce 18.01 to 19.03.1 , Upgrade docker compose 1.23 to 1.24.1

**1. upgrade Docker Compose, Docker Official Installation Method**

  ```$ sudo curl -L "https://github.com/docker/compose/releases/download/1.24.1/docker-compose-$(uname -s)-$ (uname -m)" -o /usr/local/bin/docker-compose```

This download process will be slow

Modify permissions

  ```$ sudo chmod + x / usr / local / bin / docker-compose```

View version

  ```$ docker-compose -version```

>docker-compose version 1.24.1, build 4667896b

docker compose file Corresponding version

Compose file format compatibility matrix

Compose file format	Docker Engine

1	1.9.0+

2.0	1.10.0+

2.1	1.12.0+

2.2, 3.0, 3.1, 3.2	1.13.0+

2.3, 3.3, 3.4, 3.5	17.06.0+

2.4	17.12.0+

3.6	18.02.0+

3.7	18.06.0+
 

**2. upgrade docker, docker official [upgrade](https://docs.docker.com/v18.09/install/linux/docker-ce/debian/#upgrade-docker-ce)**

  a. first uninstall the old version and update the system


  ```$ sudo apt-get remove docker docker-engine docker.io containerd runc```

  ```$ sudo apt-get update```

```$ sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common```


  b. Install key management and download related tools

  ```$ sudo apt-get install apt-transport-https ca-certificates curl gnupg2 software-properties-common```

  c. Download and install the key

  ```$ curl -fsSL https://download.docker.com/linux/debian/gpg | sudo apt-key add-```

**After installation, it will prompt " OK "**

  d. Check whether the key is successfully installed and successfully prompt the content dongge @ dongge-PC: ~ 

  ```$ sudo apt-key fingerprint 0EBFCD88```
  ```pub rsa4096 2017-02-22 [SCEA]```
  ```9DC8 5822 9FC7 DD38 854A E2D8 8D81 803C 0EBF CD88```
  ```uid [ Unknown ] Docker Release (CE deb) <docker@docker.com >```
  ```sub rsa4096 2017-02-22 [S]```

  e. Add docker-ce software source to source.list

  ```$ sudo add-apt-repository "deb [arch = amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/debian wheezy stable"```

>// Official source 
>// sudo add-apt-repository  "deb [arch = amd64] https://download.docker.com/linux/debian wheezy stable"

>// 15.11 will prompt  aptsources.distro.NoDistroTemplateException: Error: could not find a distribution template for Deepin/stable 
>// Here we can add a line by editing sudo vim /etc/apt/sources.lis t , the reason is unknown

```$ sudo add-apt-repository "deb [arch = amd64] https://mirrors.ustc.edu.cn/docker-ce/linux/debian stretch stable"```


  f. update the system again

  ```$ sudo apt-get update```

  g.install docker ce

```$ sudo apt-get install docker-ce docker-ce-cli containerd.io```

**After successful installation View docker version**

  ```$ docker version```
  
        Client: Docker Engine-Community
        Version: 19.03.1
        API version: 1.40
        Go version: go1.12.5
        Git commit: 74b1e89
        Built: Thu Jul 25 21:22:03 2019
        OS / Arch: linux / amd64
        Experimental: false
         
        Server: Docker Engine-Community
        Engine:
          Version: 19.03.1
          API version: 1.40 (minimum version 1.12)
          Go version: go1.12.5
          Git commit: 74b1e89
          Built: Thu Jul 25 21:20:35 2019
          OS / Arch: linux / amd64
          Experimental: false
        containerd:
          Version: 1.2.6
          GitCommit: 894b81a4b802e4eb2a91d1ce216b8817763c29fb
        runc:
          Version: 1.0.0-rc8
          GitCommit: 425e105d5a03fabd737a126ad93d62a9eeede87f
        docker-init:
          Version: 0.18.0
          GitCommit: fec3683
