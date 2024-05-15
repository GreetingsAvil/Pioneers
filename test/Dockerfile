# syntax=docker/dockerfile:1
FROM ros:humble-ros-core-jammy
ENV ROS_DISTRO=humble
#SHELL ["/bin/bash", "-c"]
ARG USERNAME=group6
#ARG USER_UID=152


RUN mkdir project

WORKDIR /project
# install bootstrap tools
RUN apt-get update -y && apt-get install --no-install-recommends -y \
    build-essential \
    git \
    python3-colcon-common-extensions \
    python3-colcon-mixin \
    python3-rosdep \
    python3-vcstool \
    && rm -rf /var/lib/apt/lists/*
  
RUN apt install -y doxygen build-essential 
RUN git clone https://github.com/reedhedges/AriaCoda.git
RUN cd AriaCoda && make && make install
# bootstrap rosdep
RUN rosdep init && \
  rosdep update --rosdistro humble
#$ROS_DISTRO

# setup colcon mixin and metadata
RUN colcon mixin add default \
      https://raw.githubusercontent.com/colcon/colcon-mixin-repository/master/index.yaml && \
    colcon mixin update && \
    colcon metadata add default \
      https://raw.githubusercontent.com/colcon/colcon-metadata-repository/master/index.yaml && \
    colcon metadata update

#install pip and wget
#RUN apt install wget && wget https://bootstrap.pypa.io/get-pip.py && python3 ./get-pip.py 

# install ros2 packages
RUN apt-get update && apt-get install -y --no-install-recommends \
    ros-humble-ros-base=0.10.0-1* \
    && rm -rf /var/lib/apt/lists/*

#RUN apt-get install ros-humble-joy ros-humbler-joy-drivers

COPY . /project
#RUN git clone https://github.com/GreetingsAvil/Pioneers

RUN sudo apt-get update 
#RUN apt-get install doxygen
    #&& sudo apt install -y joystick jstest-gtk evtest 
RUN apt-get install -y ros-humble-joy-linux && apt-get install -y ros-humble-teleop-twist-joy && apt-get install -y ros-humble-rviz2
RUN rosdep install --from-paths src --ignore-src --rosdistro=humble -y

#COPY ./ariaNode /project/AriaCoda/examples

#RUN cd AriaCoda && make && make install 
RUN echo "xhost +" >> ~/.bashrc
#RUN source /opt/ros/humble/setup.bash 

#RUN source /project/install/setup.bash


#export LD_LIBRARY_PATH=`pwd`/lib
#cd examples
#make simpleConnect
#./simpleConnect
