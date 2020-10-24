# Build OS
Ubuntu 20.04

# Install Docker

# Attach external volume as /data

# Install Portainer

# Requires local-persist on Ubuntu
https://github.com/MatchbookLab/local-persist

```sudo curl -fsSL https://raw.githubusercontent.com/MatchbookLab/local-persist/master/scripts/install.sh | sudo bash```

# Setup Volume
(within Portainer or bash)

```sudo docker volume create -d local-persist -o mountpoint=/data/graylog --name=data-graylog```

# Ready to install GrayLog
Follow instructions on Readme
