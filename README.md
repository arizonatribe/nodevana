# Nodevana

A NodeJs Alpine image with bash and git as the only packages. This works well as a _base_ image for any NodeJs application. Just pull it by name on the `FROM` line in your own `Dockerfile`.

# Dependencies

Docker and Docker-Compose are required to run this application, which are packaged together [for Mac](https://www.docker.com/docker-mac) and [Windows](https://www.docker.com/docker-windows) users. For Linux users (unless [on Ubuntu](https://www.docker.com/docker-ubuntu)), follow the instructions for installing  the [Docker Engine](https://docs.docker.com/engine/installation/) and [Docker Compose](https://docs.docker.com/compose/install/).

# Building the Docker Image

Run the following from the command line at the root of this directory:

```
make docker
```

That command will build an image (using the `Dockerfile` "recipe" in this project folder) from which containers can be created.

# Running the Container

This container can be run by creating a Docker Compose file (yaml) OR manually from the command line like this:

```bash
docker run --name=nodevana -d nodevana
```

# Environment variables

The following are available but are optional (since they have default values already set in the `Dockerfile`), however if you change one of the VERSION/DOWNLOAD_ variables, you will need to change all three of them.

* __BUILD_PACKAGES__ - A list of Alpine build packages to install (defaults to just the three: "bash build-base git").
