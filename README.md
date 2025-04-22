# Yadak Proxy

Base github project for the Yadak Proxy project is [here](https://github.com/gpt4thewin/docker-nginx-openai-api-cache.git).

## how to setup:

# install docker

```bash
sudo apt-get update
sudo apt-get install ca-certificates curl
sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc
```

# Add the repository to Apt sources:

```bash
echo \
 "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu \
 $(. /etc/os-release && echo "${UBUNTU_CODENAME:-$VERSION_CODENAME}") stable" | \
 sudo tee /etc/apt/sources.list.d/docker.list > /dev/null
sudo apt-get update

sudo apt-get install docker-ce docker-ce-cli containerd.io docker-buildx-plugin docker-compose-plugin docker-compose

sudo docker run hello-world

sudo apt install -y git
```

# clone repo

```bash
git clone <repo>
cd yadak-proxy
```

# update nginx.conf if needed

```bash
nano nginx.conf
```

# start the container

```bash
docker-compose up -d
```

# check images

```bash
docker images
```

# check containers

```bash
docker ps -a
```

# check docker logs

```bash
docker logs -f openai-cache-proxy
```

# docker should be running at "http://ip:81" by default

# allow access for firewall

```bash
sudo ufw allow 81/tcp

sudo ufw reload
```
