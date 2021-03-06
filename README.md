# Preface
  Docker private registry V2 and it's frontend UI

# Prerequisites
## install docker
see https://docs.docker.com/engine/installation/   
In case of installation on Ubuntu 14.04(LTS):  
```shell
sudo apt-get update && sudo apt-get -y dist-upgrade
curl -fsSL https://get.docker.com/ | sh
```

## install docker-compose
see https://github.com/docker/compose/releases or https://docs.docker.com/compose/    

for example:
```shell
sudo su
[sudo] password for user-name: (your password)
curl -L https://github.com/docker/compose/releases/download/1.7.1/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

## SSL settings

### If you don't have your server certification
create self-signed certificate and copy to ./nginx . You can use next command.

```
sudo ./set-selfsigned-cert
```

In this case, need to set docker option like followings to **clients which use this registry server**.
In the case of Ubuntu14.04: add following to /etc/default/docker

```
DOCKER_OPTS="--insecure-registry {registry server name or IP address}"
```

### If you have your server certification
copy your server cert and key to ./nginx, as server.crt and server.key
```
cp {your-server-private-key} nginx/server.key
cp {your-server-certificate} nginx/server.crt
```

## Basic authentication(optional)
To be done.

## Build 
execute

```
docker-compose build
```

# How to run registry and frontend
execute

```
docker-compose up -d 
```

# How to use registry
ex.

```
sudo docker pull hello-world
sudo docker tag hello-world {your registry server name}/test/hello-world
sudo docker push {your registry server name}/test/hello-world
sudo docker rmi {your registry server name}/test/hello-world
sudo docker pull {your registry server name}/test/hello-world
```

# How to use frontend

brows http://{your registry server name}/   
or   
brows https://{your registry server name}/   



# Refferences
* https://docs.docker.com/
* https://github.com/kwk/docker-registry-frontend
* https://github.com/opskumu/docker-registry-compose
