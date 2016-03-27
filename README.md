# Preface
  Docker private registry V2 and it's frontend UI

# Prerequisites
## install docker
see https://docs.docker.com/engine/installation/   
In case of installation on Ubuntu 14.04(LTS):  
```shell
sudo apt-get update && sudo apt-get dist-upgrade
curl -fsSL https://get.docker.com/ | sh
```

## install docker-compose
see https://docs.docker.com/compose/  
for example:
```shell
sudo su
[sudo] password for user-name: (your password)
curl -L https://github.com/docker/compose/releases/download/1.6.2/docker-compose-`uname -s`-`uname -m` > /usr/local/bin/docker-compose
chmod +x /usr/local/bin/docker-compose
```

## SSL settings

### If you like to create self-signed certificates, execute next command.

```
sudo ./set-selfsigned-cert
```
In this case, need to set docker option like followings to clients.
In the case of Ubuntu14.04: add following to /etc/default/docker

```
DOCKER_OPTS="--insecure-registry {registry server name or IP address}"
```

### If you have certificate, execute

```
cp {your-server-private-key} nginx/server.key
cp {your-server-certificate} nginx/server.crt

## Build 

```
docker-compose build
```

# Run registry and frontend
execute

```
docker-compose run -d 
```


