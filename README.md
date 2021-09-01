# dockerize_vpype
Implementing Docker images to run vpype. 

[vpype](https://github.com/abey79/vpype) is a pipeline based API and CLI for working with SVGs intended for plotters such as the Axidraw. Installing it can be tricky, however, as it relies upon a great number of dependencies. These Dockerfiles document the dependencies and allow the building of images that run vpype. Note that this is not the vpype[all] installation yet - it's tested for command line use. Additional familiarity on using Docker is up to the user. 

## Dockerfile usage
The Ubuntu image has allegedly better performance, but the Alpine image is smaller. To use, first install Docker on the host machine. Navigate to the directory, and build the docker image by running:

`docker build -t yourimagetagname .`

The folder will denote the OS. I use the images interactively by mounting a shared folder into the container. After the image is built:

`docker run -it yourimagetagname -v your/local/path:/usr/vpype/hostdir /bin/bash`

which will put you inside the docker container with vpype already installed. Containers and images can be rebuilt as necessary. You can also call vpype non interactively by omitting the `-it` and appending the `vpype` command at the end instead of `/bin/bash`


## Known issues
1. Both alpine and ubuntu fail to install PySide2 in pip, even though the documentation says that it should install. This is required for the QT-based reporting for vpype. 
2. Setting DEBIAN_FRONTEND for Ubuntu to non interactive should allow for some of the installations. 
