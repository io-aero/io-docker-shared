# IO Aero: io-raster - Raster Map Handler Library Image

This image supports the use of a Docker container containing the **io-raster** library in a Ubuntu environment.

### Table of Contents

**[1. Installed core components](#installed)**<br>
**[2. Creating a new **io-raster** container](#creating)**<br>
**[3. Working with an existing **io-raster** container](#working)**<br>

----

## <a name="installed"></a> 1. Installed core components

With the following command you can check in detail which software versions are included in the Docker image:

    apt list --installed

---

### Version 0.9.0

| Component      | Version     | Remark       | Status |
|----------------|-------------|--------------|--------|
| asdf           | v0.10.2     | base version |        | 
| GCC & G++      | 11.2.0      | base version |        | 
| Git            | 2.34.1      | base version |        | 
| GNU make       | 4.3         | base version |        | 
| io-raster      | 0.9.0       |              |        | 
| Python3        | 3.10.7      |              |        |
| Ubuntu         | 22.04.1 LTS | jammy        |        | 
| Vim            | 9.0.0000    | base version |        |
| wget           | 1.21.2      | base version |        |

---

## <a name="creating"/> 2. Getting started

### 2.1 Docker Container Administration

**Creating and running a new container:**

    docker run -it --name io-raster ioaero/io-raster:latest

**Restarting the container:**

    docker start io-raster

**Check the container is running:**
 
    docker ps

**To access a running container:**

    docker attach --detach-keys="ctrl-a" io-raster 

**Stopping a running container:**

    docker stop io-raster

### 2.2 Docker Container Usage

**Starting Python in the Virtual Environment (inside the `io-raster` container):**

    python3 -m pipenv run python3

**Make the `io_raster` module available:**

    from io_raster import raster

**Query the version of the **io-raster** library:**

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

##### Example

Creating a new Docker container named `my_io_raster` using a repository inside the Docker container:  

    docker run -it --name my_io_raster ioaero/io-raster:latest

## <a name="working"/> 3. Working with an existing **io-raster** container

### 3.1 Starting a stopped container

A previously stopped container can be started with the `docker start` command.

##### Syntax

    docker start <container_name>

##### Parameter

- **container_name** - the mandatory container identification, that is a UUID long identifier, an UUID short identifier or a previously given name

Detailed documentation for the command `docker start` can be found [here](https://docs.docker.com/engine/reference/commandline/start/).

### 3.2 Entering a running container

A running container can be entered with the `docker exec` command.

##### Syntax

    docker exec -it <container_name> <cmd>

##### Parameter

- **container_name** - the mandatory container identification, that is an UUID long identifier, an UUID short identifier or a previously given name
- **cmd** - the command to be executed in the container, e.g. `bash` for running the `bash` shell

Detailed documentation for the command `docker exec` can be found [here](https://docs.docker.com/engine/reference/commandline/exec/).
