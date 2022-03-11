FROM ghcr.io/haganelego/hma_ros_docker/hma_ros:melodic-cuda11.2.2-cudnn8-perception

SHELL [ "/bin/bash", "-c" ]


# install packages
RUN apt-get update && apt-get install -q -y --no-install-recommends \
    dirmngr \
    gnupg2 \
    curl \
    nano \
    wget \
    unzip \
    net-tools \
    iputils-ping \
    && rm -rf /var/lib/apt/lists/*

# install pip3
RUN curl -kL https://bootstrap.pypa.io/pip/3.6/get-pip.py | python3

# install pip2
RUN curl -kL https://bootstrap.pypa.io/pip/2.7/get-pip.py | python


# install depending packages (install moveit! algorithms on the workspace side, since moveit-commander loads it from the workspace)
RUN apt-get update && \
    apt-get install -y git ros-$ROS_DISTRO-moveit ros-$ROS_DISTRO-moveit-commander ros-$ROS_DISTRO-move-base-msgs ros-$ROS_DISTRO-ros-numpy ros-$ROS_DISTRO-geometry && \
    apt-get install -y ros-$ROS_DISTRO-trac-ik-kinematics-plugin && \
    apt-get install -y ros-$ROS_DISTRO-smach ros-$ROS_DISTRO-smach-viewer && \
    apt-get install -y ros-$ROS_DISTRO-gmapping && \
    apt-get install -y python-pygame python-rosdep && \
    apt-get install -y ros-$ROS_DISTRO-geometry2 && \
    apt-get install -y ros-$ROS_DISTRO-diagnostic-updater && \
    apt-get install -y ros-$ROS_DISTRO-global-planner ros-$ROS_DISTRO-dwa-local-planner && \
    apt-get install -y ros-$ROS_DISTRO-joint-state-publisher ros-$ROS_DISTRO-joint-state-publisher-gui && \
    apt-get install -y ros-$ROS_DISTRO-robot-state-publisher && \
    apt-get install -y python-catkin-tools python3-dev python3-catkin-pkg-modules python3-numpy ros-melodic-cv-bridge  && \
    apt-get install -y imagemagick && \
    apt-get clean


# python3
RUN pip3 install rospkg rosdep rosinstall && \
    pip3 install numpy matplotlib pandas && \
    pip3 install scikit-learn && \
    pip3 install open3d && \
    pip3 install opencv-contrib-python && \
    pip3 install torch torchvision && \
    pip3 install termcolor && \
    pip3 install pycocotools
    
# python2
RUN pip install rosdep rosinstall && \
    pip install numpy matplotlib pandas && \
    pip install scikit-learn && \
    pip install open3d && \
    pip install opencv-contrib-python && \
    pip install termcolor && \
    pip install call && \
    pip install popen


