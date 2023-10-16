# Human pose estimation control of the robot manipulators 

In this repository, there are all repositories that were used to enable near real-time motion control 
of the anthropomorphic arm manipulators based on the human pose estimation (HPE). 

After cloning this repository, run: 

```
git submodule update –remote
```

To update all repositories to the newest version.

Repositories contained are: 
 * `hpe_ros_package` --> initial repository for the HPE, but now contains transformation from the image space to the cartesian space based on the camera depth measurements
 * `ros_openpose` --> ROS wrapper for the openpose repo that was used to estimate pose of the human 
 * `ros_openpose_msgs` --> ROS msgs that were used to enable syncing of the depth and the HPE prediction stream to mitigate wrong depth estimations 
 * `hpe_ros_msgs` --> ROS package containing custo ROS messages that are used to create ROS messages based on the prediction 
 * `hpe_udp_ctl` --> ROS package used to create bridge between pose estimation machine and the anthropomorphic arms we want to control 
 * `dockerfiles` --> Folder that contains `Dockerfile` files that were used to create `docker` images for the environment setup 

### hpe_ros_package 

This repository contains all scripts for converting human pose pixels to the cartesian space, generating commands for UAV, arms, filtering measurements etc...

### ros_openpose

This repository contains wrapper for the `openpose` in order to enable inference based on the openpose pose estimation. 

### msgs 

All repositories that contin msgs contain ROS repositories that have custom made messages for easier communication between ROS nodes.

### Instructions: 

Installation procedure is following: 
 1. First download this repository 
 2. Build corresponding docker files, one is used for the `realsense` camera, and another one is used for the HPE and command generation (commands provided in READMEs)
 3. Copy ROS packages from this repository to the docker image created from the `Dockerfile.hpe` into `catkin_ws` workspace in the Docker (`docker cp <ROS_pkg_name> <docker_img>:/home/developer/catkin_ws`) 
 4. Use tmuxinator script to run all neccessary components of the system (camera, ros_openpose, command generation, kalman filtering...) 

If there are any questions, open issue or contact me via e-mail: `filip.zoric@fer.hr`. 

Video of the experiments can be found [here](https://www.youtube.com/watch?v=Et0COkuk6Es&ab_channel=LaricsLab). 
