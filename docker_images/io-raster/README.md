# IO-Aero: IO-RASTER - Raster Map Handler Library Image

This image supports the use of a Docker container containing the **IO-RASTER** library in a Ubuntu environment.

### Table of Contents

**[1. Installed core components](#installed)**<br>
**[2. Getting started](#started)**<br>

## <a name="installed"></a> 1. Installed core components

With the following command you can check in detail which software versions are included in the Docker image:

    apt list --installed

### Version 0.9.1

| Component      | Version     | Remark       | Status |
|----------------|-------------|--------------|--------|
| asdf           | v0.10.2     | base version |        | 
| GCC & G++      | 11.2.0      | base version |        | 
| Git            | 2.34.1      | base version |        | 
| GNU make       | 4.3         | base version |        | 
| IO-RASTER      | 0.9.1       |              |        | 
| Python3        | 3.10.7      |              |        |
| Ubuntu         | 22.04.1 LTS | jammy        |        | 
| Vim            | 9.0.0000    | base version |        |
| wget           | 1.21.2      | base version |        |

### Version 0.9.0

| Component      | Version     | Remark       | Status |
|----------------|-------------|--------------|--------|
| asdf           | v0.10.2     | base version |        | 
| GCC & G++      | 11.2.0      | base version |        | 
| Git            | 2.34.1      | base version |        | 
| GNU make       | 4.3         | base version |        | 
| IO-RASTER      | 0.9.0       |              |        | 
| Python3        | 3.10.7      |              |        |
| Ubuntu         | 22.04.1 LTS | jammy        |        | 
| Vim            | 9.0.0000    | base version |        |
| wget           | 1.21.2      | base version |        |

## <a name="started"/> 2. Getting started

### 2.1 Docker Container Administration

Creating and running a new container:

    docker run -it --name my_io_raster ioaero/io-raster:latest

Restarting the container:

    docker start my_io_raster

Check the container is running:
 
    docker ps

To access a running container:

    docker attach --detach-keys="ctrl-a" my_io_raster 

Stopping a running container:

    docker stop my_io_raster

### 2.2 Docker Container Usage

Starting Python in the Virtual Environment (inside the **IO-RASTER** container):

    python3 -m pipenv run python3

Make the `io_raster` module available:

    from io_raster import raster

Query the version of the **IO-RASTER** library:

    raster.version()

### 2.3 Detailed syntax

A new container can be created with the `docker run` command.

##### Syntax

    docker run -it 
               [--name <container_name>] \
               ioaero/io-raster[:<version>] 
               [<cmd>]

##### Parameters

- **container_name** - an optional container identification
- **version** - an optional version number of the image or the constant `latest`
- **cmd** - an optional command to be executed in the container, default is `bash` for running the `bash` shell

Detailed documentation for the command `docker run` can be found [here](https://docs.docker.com/engine/reference/run/).
