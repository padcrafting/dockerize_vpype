# dockerize_vpype
Implementing Docker images to run vpype. 

[vpype](https://github.com/abey79/vpype) is an pipeline based API and CLI for working with SVGs intended for plotters such as the Axidraw. Installing it can be tricky, however, as it relies upon a great number of dependencies. An alternative would be to create Docker images that containerize the installation of vpype (along with any other plug-ins) which makes the whole package more portable. 

## Base OS
The plan is to implement this on the base alpine and Ubuntu images. Arguably, the ubuntu image has better performance, but the alpine image is smaller. 

## Known issues
1. Ubuntu uses the apt-get package manager, and installing python3 requires some interaction. One solution is to create an intermediate image with just python3 on ubuntu, and use that as the base to build the rest of the dockerfile
