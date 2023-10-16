# Human pose estimation control of the robot manipulators 

In this repository, there are all repositories that were used to enable near real-time motion control 
of the anthropomorphic arm manipulators based on the human pose estimation (HPE). 

Before starting, run: 

```
git submodule update –remote
```

To update all repositories to the newest version.

Repositories contained are: 
 * `hpe_ros_package` --> initial repository for the HPE, but now contains transformation from the image space to the cartesian space based on the camera depth measurements 
 * `ros_openpose` --> ROS wrapper for the openpose repo that was used to estimate pose of the human 
 * `ros_openpose_msgs` --> ROS msgs that were used to enable syncing of the depth and the HPE prediction stream to mitigate wrong depth estimations 
 * `hpe_ros_msgs` --> ROS package containing custo ROS messages that are used to create ROS messages based on the prediction 
 * `dockerfiles` --> Folder that contains `Dockerfile` files that were used to create `docker` images for the environment setup 

Installation procedure is following: 
 1. First download this repository 
 2. Build corresponding docker files, one is used for the `realsense` camera, and another one is used for the HPE and command generation 
 3. Copy ROS packages from this repository to the docker image created from the `Dockerfile.hpe` into `catkin_ws` workspace in the Docker 
 4. Use tmuxinator script to run all neccessary components of the system (camera, ros_openpose, command generation, kalman filtering...) 

If there are any questions, open issue or contact me via e-mail: `filip.zoric@fer.hr`. 

