################################################################################
# CMake
################################################################################
cmake_minimum_required(VERSION 2.8.3)
project(krb100m_msg)

################################################################################
# Packages
################################################################################
find_package(catkin REQUIRED COMPONENTS
  message_generation
  std_msgs
  sensor_msgs
  std_srvs
  roscpp
  rospy
  dynamic_reconfigure
)

################################################################################
# Declare ROS messages, services and actions
################################################################################
add_message_files(
  FILES
  SenState.msg
  Sp25.msg
  VersionInfo.msg
  PanoramaImg.msg
  Sound.msg
  Dynamic.msg
)

add_service_files(
  DIRECTORY srv
  FILES
  TakePanorama.srv
  SetFollowState.srv
)


generate_messages(
  DEPENDENCIES
  std_msgs
  sensor_msgs
)

generate_dynamic_reconfigure_options(cfg/krb100m.cfg)

################################################################################
# Declare ROS dynamic reconfigure parameters
################################################################################

################################################################################
# Catkin specific configuration
################################################################################
catkin_package(
  CATKIN_DEPENDS std_msgs sensor_msgs std_srvs message_runtime
)

################################################################################
# Build
################################################################################

################################################################################
# Install
################################################################################

################################################################################
# Test
################################################################################
