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

- this command will up and build too.
- `make start`

### Than i have to create network.
- `docker network create itlogiko-network`
- `sudo docker compose up --build`
- in UI i alos have to install `sudo npm i` for ubunto PC.

### Database migration.
- for to enter container.
- `make shell`

- to seed first exit `exit` command than.
- `make seed` to seed database.

### Some useful command
- to see or check the list of running container.
- `docker ps`

- or `sudo docker ps`

- Delete restore the file from your branch. File should have content from develop branch.
- `git checkout origin/develop -- /path/to/file`

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
- `docker-compose up --build`
- `sudo docker-compose up --build`

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



## Test git cherry-pick or git rebase.
- `git checkout -b 1051-new 1051-existing`
- `git rebase develop -i`
- `git rebase --continue`

- NOTE: Choose 1051 commits in interactive mode
- `git checkout -b 1051-new develop`
- `git cherry-pick \
  commid-id-1051-1 \
  commid-id-1051-2 \
  commid-id-1051-3`

- `git cherry-pick --continue`
- NOTE: Find 1051 commits from branch or merge request
- https://gitlab.com/group/repository/-/commit/commit-id
- Test git cherry-pick or git rebase.
- Create a branch xyz from develop.
- Push two commits.
- Create a branch abc from branch xyz.
- Push two commits.
- Follow cherry pick or rebase commands.

## Podman Install process in Ubuntu PC,after i already have installed docker.
- ```sudo apt update
sudo apt install -y podman
```

- Verify the installation:
- `podman --version`

- install podman compose
- `sudo apt install -y podman-compose`

- for UI
- `podman network create itlogiko-network`
- `sudo podman compose up --build`

for API
- `systemctl --user start podman.socket`
- `systemctl --user start podman.socket`
- `systemctl --user status podman.socket`
- `podman compose version`
- `sudo podman compose up --build`

### Docker uninstalled from ubuntu PC
- `systemctl status docker`
- `sudo systemctl disable docker`
- `sudo systemctl stop docker`

- `sudo systemctl stop docker.socket
sudo systemctl stop docker.service`
- `sudo systemctl disable docker.socket
sudo systemctl disable docker.service`
- `systemctl status docker`

- `sudo systemctl start docker.service docker.socket`

- `docker system prune --all --force --volumes`

- `sudo systemctl stop docker.service docker.socket`

### Check container running in background(sudo issue in ubuntu).

- Step-1: Check if any process is running or not:

- sudo lsof -iTCP:{port number} -sTCP:LISTEN

- Step-2: If running kill: sudo kill -9 {pid}

- Step-3: make stop

- Step-4: make start

### After update laravel latest version
- `podman compose up`
- than `make start` it should worked
- for UI also `make composer-install`
