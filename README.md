# Simple Node
## Overview
This is a very simple, bare-bones NodeJS project created for you to use with Docker.

## Local Setup
* Install dependencies: `npm install`
* Run server: `node server.js`

## Container Setup
~~* Build image: `docker build .`~~
~~* Run container with image: `docker run {image_id}` where `image_id` can be retrieved by running `docker images` and found under the column `IMAGE ID`~~

Run the following to build the image and push it to dockerhub.com
```
docker build -t simple-node .
docker tag simple-node aldolinux/simple-node
docker login --username=aldolinux
docker push aldolinux/simple-node
```

## Container teardown
* Remove container: `docker kill {container_id}` where `container_id` can be retrieved by running `docker ps` and found under the column `CONTAINER ID`


# Kubernetes Cluster in AWS

In order to setup the EKS cluster in AWS it is best to use the [eksctl](https://docs.aws.amazon.com/eks/latest/userguide/eksctl.html) command line utility.

1. Create the EKS Cluster:
```
eksctl create cluster \
--name simple-node-aldo \
--region us-east-2 \
--nodegroup-name nodegroup-simple-node-aldo \
--node-type t2.micro \
--nodes 2

```
