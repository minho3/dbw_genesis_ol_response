cmake_minimum_required(VERSION 2.8.3)
project(dbw_genesis_ol_response)

find_package(catkin REQUIRED COMPONENTS
  geometry_msgs
  nav_msgs
  roscpp
  rospy
  std_msgs
  message_generation
)

################################################
## Declare ROS dynamic reconfigure parameters ##
################################################

## To declare and build dynamic reconfigure parameters within this
## package, follow these steps:
## * In the file package.xml:
##   * add a build_depend and a run_depend tag for "dynamic_reconfigure"
## * In this file (CMakeLists.txt):
##   * add "dynamic_reconfigure" to
##     find_package(catkin REQUIRED COMPONENTS ...)
##   * uncomment the "generate_dynamic_reconfigure_options" section below
##     and list every .cfg file to be processed

## Generate dynamic reconfigure parameters in the 'cfg' folder
# generate_dynamic_reconfigure_options(
#   cfg/DynReconf1.cfg
#   cfg/DynReconf2.cfg
# )


###########
## MSG ##
###########
#add_message_files(
#	FILES
#	MPC_cmd.msg
#)

#generate_messages(
#	DEPENDENCIES
#	std_msgs
#)

###########
## Build ##
###########

catkin_package(
	CATKIN_DEPENDS message_runtime std_msgs
)

## Specify additional locations of header files
## Your package locations should be listed before other locations
include_directories(
  include
  ${catkin_INCLUDE_DIRS}
)

# Modified C++ Program Build of Twist Controller
#add_executable(low_level_controller src/LowLevelControlNode.cpp src/LowLevelController.cpp)
#add_dependencies(low_level_controller dbw_mkz_msgs_gencpp)
#add_dependencies(low_level_controller ${${PROJECT_NAME}_EXPORTED_TARGETS})
#target_link_libraries(low_level_controller
#  ${catkin_LIBRARIES}
#)

#add_executable(twist_tester src/twist_tester.cpp)
#add_dependencies(twist_tester dbw_mkz_msgs_gencpp)
#add_dependencies(twist_tester ${PROJECT_NAME}_gencfg)
#target_link_libraries(twist_tester
#  ${catkin_LIBRARIES}
#)


#############
## Install ##
#############
# Example from Twist Tester
#install(TARGETS low_level_controller
#        RUNTIME DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
#        LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
#)

install(DIRECTORY launch
        DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
