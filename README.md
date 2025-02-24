# Docker_Document
i will document the docker install process in Ubuntu PC.

### Install process in Ubuntu PC.
- `sudo apt update
sudo apt install docker.io
sudo systemctl start docker
sudo systemctl enable docker`
- To verify version
- `docker --version`
- for make the docker image
- `docker-compose up --build`

### Than i have to create network.
- `docker network create itlogiko-network`
- `sudo docker compose up --build`

### facing issue in Ubuntu PC step to fix.
- to install docker compose
- `sudo apt update
sudo apt install docker-compose-plugin`
- than check the version of docker.
- `docker compose version`
- if still have the issue run those command.
- `sudo curl -L "https://github.com/docker/compose/releases/latest/download/docker-compose-$(uname -s)-$(uname -m)" -o /usr/local/bin/docker-compose
sudo chmod +x /usr/local/bin/docker-compose`
- `docker compose up --build`
- if still have issue
- `sudo systemctl restart docker`
- than run some command
- `sudo apt update
sudo apt install ca-certificates curl gnupg`
- `sudo install -m 0755 -d /etc/apt/keyrings
sudo curl -fsSL https://download.docker.com/linux/ubuntu/gpg -o /etc/apt/keyrings/docker.asc
sudo chmod a+r /etc/apt/keyrings/docker.asc`
- `echo "deb [arch=$(dpkg --print-architecture) signed-by=/etc/apt/keyrings/docker.asc] https://download.docker.com/linux/ubuntu $(lsb_release -cs) stable" | sudo tee /etc/apt/sources.list.d/docker.list > /dev/null`
- `sudo apt update`
- `sudo apt install docker-compose-plugin`

#### Check If Docker is Running
- `sudo systemctl status docker`
- Run Docker as Root (Temporary Fix)
- `sudo docker compose up --build`
#### Add Your User to the Docker Group (Permanent Fix)
- `sudo usermod -aG docker $USER`
- Apply the changes:
- `newgrp docker`
- Restart Docker:
- `sudo systemctl restart docker`
- Now, try running the command without sudo
- `docker compose up --build`
- Verify Your Docker Permissions
- `docker run hello-world`
#### Final Check: Pull the Image Manually
- `docker pull itlogiko/real-estate-ui`
- `docker compose up --build`