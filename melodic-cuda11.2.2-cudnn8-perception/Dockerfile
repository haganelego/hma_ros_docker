FROM ghcr.io/haganelego/hma_ros_docker/hma_ros:melodic-cuda11.2.2-cudnn8-base

# install ros packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-melodic-perception \
    && rm -rf /var/lib/apt/lists/*
