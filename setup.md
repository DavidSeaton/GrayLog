# Build OS
Ubuntu 20.04

# Install Docker



# Attach external volume as /data

# Install Portainer
REF: https://www.portainer.io/installation/

```
sudo docker volume create portainer_data
sudo docker run -d -p 8000:8000 -p 9000:9000 --name=portainer --restart=always -v /var/run/docker.sock:/var/run/docker.sock -v portainer_data:/data portainer/portainer
```

Create docker-compose.yml

```
version: '2'

services:
  portainer:
    image: portainer/portainer
    command: -H unix:///var/run/docker.sock
    restart: always
    ports:
      - 9000:9000
      - 8000:8000
    volumes:
      - /var/run/docker.sock:/var/run/docker.sock
      - portainer_data:/data

volumes:
  portainer_data:
```

# Requires local-persist on Ubuntu
https://github.com/MatchbookLab/local-persist

```sudo curl -fsSL https://raw.githubusercontent.com/MatchbookLab/local-persist/master/scripts/install.sh | sudo bash```

# Setup Volume
(within Portainer or bash)

```sudo docker volume create -d local-persist -o mountpoint=/data/graylog --name=data-graylog```

# Ready to install GrayLog
Follow instructions on Readme
