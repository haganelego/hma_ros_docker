# About this image  
RC2021用docker-image  

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
以下のリンクを参考にインストール  
https://docs.docker.com/engine/install/ubuntu/

## NVIDIA Container Toolkit  
以下のリンクを参考にインストール  
https://github.com/NVIDIA/nvidia-docker/tree/master#quickstart  

# test  
```docker
docker pull hoge
```  