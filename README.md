# CarND-LeNet-Lab
[![Udacity - Self-Driving Car NanoDegree](https://s3.amazonaws.com/udacity-sdc/github/shield-carnd.svg)](http://www.udacity.com/drive)

![LeNet-5 Architecture](lenet.png)
Implement the LeNet-5 deep neural network model.

### Dependencies
This lab requires:

* [CarND Term1 Starter Kit](https://github.com/udacity/CarND-Term1-Starter-Kit)

The lab enviroment can be created with CarND Term1 Starter Kit. Click [here](https://github.com/udacity/CarND-Term1-Starter-Kit/blob/master/README.md) for the details.



### Pull the Precompiled Docker Image from Docker Hub

A precompiled image with all dependencies required for the first 
term is available on [Docker Hub][carnd_docker_hub].

Once you have docker working, pull the image using the following command:

```sh
docker pull udacity/carnd-term1-starter-kit
```

### Run The Image as a New Container

In your shell, navigate to the directory of a project, e.g.

```bash
$ cd ~/src/CarND-LeNet-Lab
```

From within this directory, you are going to run a Jupyter server. In order
to do this you must attach to the correct port and share a local volume.

The easiest way to share a local volume is via the `pwd` command, a shell
command that prints the working directory. This command will be used
differently based on your shell.



If you're using `bash` or Docker Quickstart Terminal:

```sh
docker run -it --rm --entrypoint "/run.sh" -p 8888:8888 -v `pwd`:/src udacity/carnd-term1-starter-kit
```

Let's break this down.

`docker run` is the command a startup and run a Docker container.

`-it` forces the container to run in the foreground (interactive mode) and
provides an I/O to the container.

`--rm` removes the container once it stops running.
It prevents the buildup of stale containers once you stop them from running.

`--entrypoint "/run.sh"` tells the container to run `run.sh` when it opens.
In our case, this file activates the conda environment and opens a jupyter notebook in the background.
This is also included in the dockerfile, but sometimes does not appropriately run without this flag.

`-p 8888:8888` maps port 8888 on our local machine to port 8888 in the Docker
container, this allows us to access port 8888 in the container
by visiting `localhost:8888`.

`-v ${pwd}:/src` mounts the pwd (present working directory) to the /src
directory in the container. Basically, this lets us access files
from our local machine on the docker container.

`udacity/carnd-term1-starter-kit` is the name of the container to run.

To learn more about Docker [visit the docs](https://docs.docker.com/engine/userguide/intro/).

[carnd_docker_hub]: https://hub.docker.com/r/udacity/carnd-term1-starter-kit/

### Notes

`from tensorflow.examples.tutorials.mnist import input_data` not responsing. 
Just use the predownloaed data.