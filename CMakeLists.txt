cmake_minimum_required(VERSION 3.0.2)
project(KAIST-DP)

## Compile as C++11, supported in ROS Kinetic and newer
# add_compile_options(-std=c++11)
set(CMAKE_BUILD_TYPE "Release")

find_package(catkin REQUIRED COMPONENTS
  roscpp
  sensor_msgs
  cv_bridge
)

find_package(OpenCV REQUIRED)
find_package(realsense2 REQUIRED)

catkin_package(
#  INCLUDE_DIRS include
#  LIBRARIES image_stitching
#  CATKIN_DEPENDS roscpp sensor_msgs
#  DEPENDS system_lib
)

include_directories(
# include
  ${catkin_INCLUDE_DIRS}
  ${realsense_INCLUDE_DIR}
)

message(WARNING "OpenCV_VERSION: ${OpenCV_VERSION}")
message(WARNING "Librealsense_VERSION: ${realsense2_VERSION}")
