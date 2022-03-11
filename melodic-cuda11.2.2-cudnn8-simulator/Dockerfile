FROM ghcr.io/haganelego/hma_ros_docker/hma_ros:melodic-cuda11.2.2-cudnn8-perception

SHELL [ "/bin/bash", "-c" ]


# install depending packages (install moveit! algorithms on the workspace side, since moveit-commander loads it from the workspace)
RUN apt-get update && \
    apt-get install -y git ros-$ROS_DISTRO-moveit ros-$ROS_DISTRO-moveit-commander ros-$ROS_DISTRO-move-base-msgs ros-$ROS_DISTRO-ros-numpy ros-$ROS_DISTRO-geometry && \
    apt-get install -y ros-$ROS_DISTRO-trac-ik-kinematics-plugin && \
    apt-get install -y ros-$ROS_DISTRO-smach ros-$ROS_DISTRO-smach-viewer && \
    apt-get install -y ros-$ROS_DISTRO-gmapping && \
    apt-get install -y python-pygame python-rosdep && \
    apt-get install -y ros-$ROS_DISTRO-geometry2 && \
    apt-get install -y ros-$ROS_DISTRO-joint-state-publisher ros-$ROS_DISTRO-joint-state-publisher-gui && \
    apt-get clean

# install bio_ik
RUN source /opt/ros/$ROS_DISTRO/setup.bash && \
    mkdir -p /bio_ik_ws/src && \
    cd /bio_ik_ws/src && \
    catkin_init_workspace && \
    git clone --depth=1 https://github.com/TAMS-Group/bio_ik.git && \
    cd .. && \
    catkin_make install -DCMAKE_BUILD_TYPE=Release -DCMAKE_INSTALL_PREFIX=/opt/ros/$ROS_DISTRO -DCATKIN_ENABLE_TESTING=0 && \
    cd / && rm -r /bio_ik_ws

# python3
RUN pip3 install rospkg rosdep rosinstall && \
    pip3 install numpy matplotlib pandas && \
    pip3 install scikit-learn && \
    pip3 install open3d && \
    pip3 install opencv-contrib-python && \
    pip3 install torch torchvision && \
    pip3 install termcolor
    
# python2
RUN pip install rosdep rosinstall && \
    pip install numpy matplotlib pandas && \
    pip install scikit-learn && \
    pip install open3d && \
    pip install opencv-contrib-python && \
    pip install termcolor && \
    pip install call && \
    pip install popen


