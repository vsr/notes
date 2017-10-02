# Installation on Ubuntu

## Add docker apt repo and install
(Steps from https://docs.docker.com/engine/installation/linux/docker-ce/ubuntu/#install-using-the-repository )

```bash
sudo apt-get update

sudo apt-get install \
    apt-transport-https \
    ca-certificates \
    curl \
    software-properties-common

curl -fsSL https://download.docker.com/linux/ubuntu/gpg | sudo apt-key add -

sudo add-apt-repository \
   "deb [arch=amd64] https://download.docker.com/linux/ubuntu \
   $(lsb_release -cs) \
   stable"

sudo apt-get update

sudo apt-get install docker-ce

```


## Adding user to `docker` group

```bash
sudo usermod -aG docker ${USER}
su - ${USER}
```
