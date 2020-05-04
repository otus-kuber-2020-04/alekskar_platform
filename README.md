# alekskar_platform
alekskar Platform repository
#### HW1 

_master branch status:_  
[![Build Status](https://travis-ci.com/otus-kuber-2020-04/alekskar_platform.svg?branch=master)](https://travis-ci.com/otus-kuber-2020-04/alekskar_platform)
___
**Task 1:**
 Create Dockerfile that meet the following requirements:
- runs web server on port 8000
- as non-privileged user with uid 1001
- returns any content within /app directory

**Results:**
 > Created [Dockerfile](kubernetes-into/web/Dockerfile) that allows to build web server image
> based on nginx official docker image.
> Additional configuration files required to run as  non-privileged user and run webserver on a  custom port.
___

**Task 2:**
- create pod manifest which runs container based on images from Task 1.
- add busybox init container to pod manifest with the **command**:
 `['sh', '-c', 'wget -O- https://tinyurl.com/otus-k8s-intro | sh']` 
to dynamically create content in app folder.
- create `app` volume to share content between init and web containers. 

 **Results:**
>  Results are presented into [kubernetes-intro/web-pod.yaml](kubernetes-intro/web-pod.yaml) file
___

 **Task 3:**
- build docker image for frontend microservice in the [microservices-demo](https://github.com/GoogleCloudPlatform/microservices-demo) repo
- identify reason of `Error` status of frontend pod, create new fixed  `frontend-pod-healthy.yaml` manifest.
 
 **Results:**
 > Pod failed due to missing env variables.
 > Correct pod manifest is [frontend-pod-healthy.yaml](kubernetes-intro/frontend-pod-healthy.yaml)
