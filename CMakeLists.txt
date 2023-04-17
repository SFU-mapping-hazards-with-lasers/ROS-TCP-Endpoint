cmake_minimum_required(VERSION 2.8.3)
project(ros_tcp_endpoint)

find_package(catkin REQUIRED COMPONENTS
  rospy
  std_msgs
)

catkin_python_setup()

catkin_package(CATKIN_DEPENDS message_runtime )

# the following catkin_install_python is added to resolve issue as described:
# https://github.com/Unity-Technologies/Unity-Robotics-Hub/issues/385
# error message: "/usr/bin/env: ‘python\r’: No such file or directory"
catkin_install_python(
  PROGRAMS
    src/ros_tcp_endpoint/default_server_endpoint.py
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)