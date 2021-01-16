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
cd inferno_docker
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

### Volume mount your local instance of inferno-os source
Optionally users can modify the `docker-compose.yml' to volume mount source code from the host machine to the contianer

First replace the mkconfig file in your host machines source code with the one located in 

```bash
cp -f mkconfig <your hosts path to the inferno repo>/inferno-os/mkconfig
```

```bash
cd inferno_docker
vi docker-compose.yml
```

Uncomment the "volumes" section and provide your local path to the inferno-os repo

```
    # (optional) Volume mount your locally stored inferno-os repo
    volumes:
            - <your hosts path to the inferno repo>/inferno-os:/proj/inferno-os

```

### Display

if you have any time of display forwarding you will want to set the environement variable for DISPLAY on the host machine 

from the inferno container

``` bash
emu
wm/wm
```



## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.

## License
[MIT](https://choosealicense.com/licenses/mit/)
