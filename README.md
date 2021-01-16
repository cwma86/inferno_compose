# Inferno Compose

Inferno Compose is a docker compose script to build and deploy a docker container with the inferno OS

## Installation

Install Docker (developed for version 19.03.8)

```bash
sudo apt-get install -y docker
```
Install Docker-compose (developed for version 1.25.0)

```bash
sudo apt-get install -y docker-compose
```
## Usage

Starting the container

```bash
docker-compose up
```

Bash terminal to running contianer

```bash
docker exec -it inferno_docker_inferno_1 bash
```

running inferno (from container bash terminal)
```bash
emu
```
Building inferno (from container bash terminal)

```bash
cd /proj/inferno-os
mk
```


## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
