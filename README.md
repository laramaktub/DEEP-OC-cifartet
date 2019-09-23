<div align="center">
<img src="https://marketplace.deep-hybrid-datacloud.eu/images/logo-deep.png" alt="logo" width="300"/>
</div>

# DEEP-OC-cifartet

[![Build Status](https://jenkins.indigo-datacloud.eu:8080/buildStatus/icon?job=Pipeline-as-code/DEEP-OC-org/DEEP-OC-cifartet/master)](https://jenkins.indigo-datacloud.eu:8080/job/Pipeline-as-code/job/DEEP-OC-org/job/DEEP-OC-cifartet/job/master)

This is a container that will simply run the DEEP as a Service API component,
with cifartet (src: [cifartet](https://github.com/laramaktub/cifartet)).

    
## Running the container

### Directly from Docker Hub

To run the Docker container directly from Docker Hub and start using the API
simply run the following command:

```bash
$ docker run -ti -p 5000:5000 -p 6006:6006 laramaktub/deep-oc-cifartet
```

This command will pull the Docker container from the Docker Hub
[laramaktub](https://hub.docker.com/u/laramaktub/) repository and start the default command (deepaas-run --listen-ip=0.0.0.0).

### Running via docker-compose

docker-compose.yml allows you to run the application with various configurations via docker-compose, for example:

```bash
$ docker-compose up cifartet
```

**N.B!** docker-compose.yml is of version '2.3', one needs docker 17.06.0+ and docker-compose ver.1.16.0+, see https://docs.docker.com/compose/install/

If you want to use Nvidia GPU, you need nvidia-docker and docker-compose ver1.19.0+ , see [nvidia/FAQ](https://github.com/NVIDIA/nvidia-docker/wiki/Frequently-Asked-Questions#do-you-support-docker-compose)


### Building the container

If you want to build the container directly in your machine (because you want
to modify the `Dockerfile` for instance) follow the following instructions:

Building the container:

1. Get the `DEEP-OC-cifartet` repository (this repo):

    ```bash
    $ git clone https://github.com/laramaktub/DEEP-OC-cifartet
    ```

2. Build the container:

    ```bash
    $ cd DEEP-OC-cifartet
    $ docker build -t laramaktub/deep-oc-cifartet .
    ```

3. Run the container:

    ```bash
    $ docker run -ti -p 5000:5000 -p 6006:6006 laramaktub/deep-oc-cifartet
    ```

These three steps will download the repository from GitHub and will build the
Docker container locally on your machine. You can inspect and modify the
`Dockerfile` in order to check what is going on. For instance, you can pass the
`--debug=True` flag to the `deepaas-run` command, in order to enable the debug
mode.


## Connect to the API

Once the container is up and running, browse to `http://localhost:5000` to get
the [OpenAPI (Swagger)](https://www.openapis.org/) documentation page.
