# IO Aero: io-aero-dev - IO Aero Development Image

This image supports the use of a Docker container for the development of the **IO Aero** software in an Ubuntu environment.

### Table of Contents

**[1. Installed core components](#installed)**<br>
**[2. Creating a new io-aero-dev container](#creating)**<br>
**[3. Working with an existing io-aero-dev container](#working)**<br>

----

## <a name="installed"/> 1. Installed core components

With the following command you can check in detail which software versions are included in the Docker image:

    apt list --installed

---

### Version 0.9.0

| Component      | Version     | Remark                           | Status |
|----------------|-------------|----------------------------------|--------|
| asdf           | v0.10.2     | base version                     |        | 
| Docker Desktop | 20.10.17    | base version [Docker Image & VM] |        | 
| dos2unix       | 7.4.2       | base version                     |        | 
| GDAL           | 3.5.2       |                                  |        | 
| Git            | 2.34.1      | base version                     |        | 
| GNU make       | 4.3         | base version                     |        | 
| Python3        | 3.10.7      |                                  |        |
| Rasterio       | 1.3.2       |                                  |        |
| Ubuntu         | 22.04.1 LTS | base version [jammy]             |        | 
| Vim            | 9.0.0000    | base version                     |        |

---

## <a name="creating"/> 2. Creating a new io-aero-dev container

### 2.1 Getting started

    > REM Assumptions:
    > REM   - the name of the Docker container should be: my_io_aero_dev
    > REM   - you want to use the latest version of the io-aero-dev image
    > docker run --name my_io_aero_dev ioaero/io-aero-dev:latest
            
    > REM Stopping the container
    > docker stop my_io_aero_dev
    
    > REM Restarting the container
    > docker start my_io_aero_dev

    > REM Entering a running container
    > docker exec -it my_io_aero_dev bash

### 2.2 Detailed syntax

A new container can be created with the `docker run` command.

##### Syntax

    docker run -it 
               [--name <container_name>] \
               ioaero/io-aero-dev[:<version>] 
               [<cmd>]

##### Parameters

- **container_name** - an optional container identification
- **version** - an optional version number of the image or the constant `latest`
- **cmd** - an optional command to be executed in the container, default is `bash` for running the `bash` shell

Detailed documentation for the command `docker run` can be found [here](https://docs.docker.com/engine/reference/run/).

##### Example

Creating a new Docker container named `my_io_aero_dev` using a repository inside the Docker container:  

    `docker run -it --name my_io_aero_dev ioaero/io-aero-dev:latest`

## <a name="working"/> 3. Working with an existing io-aero-dev container

### 3.1 Starting a stopped container

A previously stopped container can be started with the `docker start` command.

##### Syntax

    docker start <container_name>

##### Parameter

- **container_name** - the mandatory container identification, that is an UUID long identifier, an UUID short identifier or a previously given name

Detailed documentation for the command `docker start` can be found [here](https://docs.docker.com/engine/reference/commandline/start/).

### 3.2 Entering a running container

A running container can be entered with the `docker exec` command.

##### Syntax

    docker exec -it <container_name> <cmd>

##### Parameter

- **container_name** - the mandatory container identification, that is an UUID long identifier, an UUID short identifier or a previously given name
- **cmd** - the command to be executed in the container, e.g. `bash` for running the `bash` shell

Detailed documentation for the command `docker exec` can be found [here](https://docs.docker.com/engine/reference/commandline/exec/).
