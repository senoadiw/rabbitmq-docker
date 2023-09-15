# rabbitmq-docker
Run the latest RabbitMQ 3.x with Management plugin on Docker.

Based on the following images:
* https://hub.docker.com/_/rabbitmq/

## Requirements
* Docker and Docker Compose installed
  * https://docs.docker.com/engine/install/
* for Linux: the user must belong the docker group to allow running `docker` without `sudo` privilege
  * `sudo usermod -aG docker ${USER}`

## How to run
SSH to the target server and run:
```
git clone https://github.com/senoadiw/rabbitmq-docker.git

cd rabbitmq-docker

cp .env.sample .env

# edit the default settings (optional)
nano .env

# bring up the container
docker compose up -d

# check the logs and wait a moment for the container to initialize
docker compose logs -f

# done!

# access bash shell on the container
docker compose exec -it rabbitmq bash

# to stop the container
docker compose stop

# to start the container
docker compose up -d

# to delete the container
docker compose down
```

## Daemon and Management
The RabbitMQ daemon will listen on the default port of 5672.

Management plugin is available by accessing `http://localhost:15672` and entering the following details:
* Username: refer to the `.env` file
* Password: refer to the `.env` file
