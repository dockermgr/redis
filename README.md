## 👋 Welcome to redis 🚀  

redis README  
  
  
## Requires scripts to be installed  

```shell
 sudo bash -c "$(curl -q -LSsf "https://github.com/systemmgr/installer/raw/main/install.sh")"
 systemmgr --config && systemmgr install scripts  
```

## Automatic install/update  

```shell
dockermgr update redis
```

OR

```shell
mkdir -p "$HOME/.local/share/srv/docker/redis/dataDir"
git clone "https://github.com/dockermgr/redis" "$HOME/.local/share/CasjaysDev/dockermgr/redis"
cp -Rfva "$HOME/.local/share/CasjaysDev/dockermgr/redis/dataDir/." "$HOME/.local/share/srv/docker/redis/dataDir/"
```

## via command line  

```shell
docker pull casjaysdevdocker/redis:latest && \
docker run -d \
--restart always \
--privileged \
--name casjaysdevdocker-redis \
--hostname casjaysdev-redis \
-e TZ=${TIMEZONE:-America/New_York} \
-v $HOME/.local/share/srv/docker/redis/dataDir/data:/data:z \
-v $HOME/.local/share/srv/docker/redis/dataDir/config:/config:z \
-p 80:80 \
casjaysdevdocker/redis:latest
```

## via docker-compose  

```yaml
version: "2"
services:
  redis:
    image: casjaysdevdocker/redis
    container_name: redis
    environment:
      - TZ=America/New_York
      - HOSTNAME=casjaysdev-redis
    volumes:
      - $HOME/.local/share/srv/docker/redis/dataDir/data:/data:z
      - $HOME/.local/share/srv/docker/redis/dataDir/config:/config:z
    ports:
      - 80:80
    restart: always
```

## Author  

📽 dockermgr: [Github](https://github.com/dockermgr) 📽  
🤖 casjay: [Github](https://github.com/casjay) [Docker](https://hub.docker.com/r/casjay) 🤖  
⛵ CasjaysDevDocker: [Github](https://github.com/casjaysdevdocker) [Docker](https://hub.docker.com/r/casjaysdevdocker) ⛵  
