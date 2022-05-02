# KAIST-DP 
## KAIST Divergence Path Dataset

<img src="https://github.com/SungJaeShin/KAIST-DP/blob/main/results/HW_configuration.png" width = 80% height = 80% div align=center />


**Description**
- Intel Realsense D455 x3
- Xsens MtTI-300 IMU
- Velodyne LiDAR VLP 16


**For using PanoNetVLAD**
- [PanoNetVLAD](https://github.com/SungJaeShin/PanoNetVLAD.git): Loop Closing in Continuous Visual Space represented with Panoramic View ​


## 1. Prerequisites
### 1.1 **Ubuntu** and **ROS**
Ubuntu 64-bit 16.04 or 18.04.
ROS Kinetic or Melodic. [ROS Installation](http://wiki.ros.org/ROS/Installation)


### 1.2. **Realsense SDK**
Follow [Realsense SDK](https://github.com/IntelRealSense/realsense-ros)



### 1.3 **Xsense Driver**
Follow [Xsens Driver](https://github.com/ethz-asl/ethzasl_xsens_driver)


## 2. Build KAIST-DP dataset
Clone the repository and catkin_make:
```
    cd ~/catkin_ws/src
    git clone https://github.com/SungJaeShin/KAIST-DP.git
    cd ../../
    catkin config -DCMAKE_BUILD_TYPE=Release
    catkin build KAIST-DP
    source ~/catkin_ws/devel/setup.bash 
```
(if you fail in this step, try to find another computer with clean system or reinstall Ubuntu and ROS)


## 3. Get KAIST-DP dataset
Open two terminals, run multi camera and IMU and get the bag file respectively:
```
    roslaunch KAIST-DP three_cams.launch 
    
    roscd KAIST-DP
    cd sh_files/
    sh get_kaist_dp_bag.sh
```
(then, bag file save at bag folder !!)


## 4. Results of sensor data applying LIO-SAM and VINS-Fusion
- For LiDAR data applied [LIO-SAM](https://github.com/TixiaoShan/LIO-SAM.git)
    <img src="https://github.com/SungJaeShin/KAIST-DP/blob/main/results/lio_sam.png" width = 80% height = 80% div align=center />


- For Camera data applied [VINS-Fusion](https://github.com/HKUST-Aerial-Robotics/VINS-Fusion.git)
    <img src="https://github.com/SungJaeShin/KAIST-DP/blob/main/results/vins_fusion.png" width = 80% height = 80% div align=center />


## 5. Acknowledgements
These cameras and IMU are provided URL of KAIST.

