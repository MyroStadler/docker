# docker

This is the common docker repo and contains simple docker images with no large dependencies.

Each directory here is independent, favouring small build context upload footprint over inclusion of common build assets. 
Therefore you should specify the build context as e.g. `./myproject` instead of just `.`

If an asset is repeated in many build directories and it is large 
(bearing in mind that symlinks are not allowed in docker build contexts) 
then consider building the asset into a parent FROM image.

Build an image from the dockerfile in directory `myproject` and push image:

        docker build --no-cache -t mydockerhubidentity/myproject:latest ./myproject
        docker push mydockerhubidentity/myproject:latest

`.dockerignore` is included just in case you use the root as build context for any reason, 
it would not be used if using the above build strategy
since the build context `./myproject` does not contain it.