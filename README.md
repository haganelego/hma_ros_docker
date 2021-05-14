# About this image  
Docker image for RC2021.   
In detail, please show below link.  
https://github.com/users/haganelego/packages/container/package/hma_ros_docker%2Fhma_ros    

# requirement  
- x86_64 CPU
- docker  
- NVIDIA Container Toolkit  
- GPU
- nvidia-driver:450.36.06以上   

# image description  
- Ubuntu:18.04.4  
- python2:2.7.17  
- python3:3.6.9  
- cuda:11.0
- cudnn:8
- pip2:20.3.4  
- pip3:21.1.1  

# docker instlation 
## docker  
Refer to the following link for installation  
https://docs.docker.com/engine/install/ubuntu/

## NVIDIA Container Toolkit  
Refer to the following link for installation  
https://github.com/NVIDIA/nvidia-docker/tree/master#quickstart  

# test  
1. Pull docker-image  
```bash  
docker pull ghcr.io/haganelego/hma_ros_docker/hma_ros:melodic-cuda11.0-cudnn8-base
```  
2. Check nvidia-smi is available in container  
```bash
docker run --rm --gpus all ghcr.io/haganelego/hma_ros_docker/hma_ros:melodic-cuda11.0-cudnn8-base nvidia-smi
```  
3. Check cuda is available in container
```bash
docker run --rm --gpus all ghcr.io/haganelego/hma_ros_docker/hma_ros:melodic-cuda11.0-cudnn8-base nvcc -V
```  