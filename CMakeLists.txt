# %Tag(FULLTEXT)%
cmake_minimum_required(VERSION 2.8.3)
project(homework4)

## Find catkin and any catkin packages
find_package(catkin REQUIRED COMPONENTS roscpp rospy std_msgs genmsg)
find_package( OpenCV REQUIRED )


## Declare ROS messages and services
##add_message_files(FILES Num.msg)
##add_service_files(FILES AddTwoInts.srv)

## Generate added messages and services
generate_messages(DEPENDENCIES std_msgs)

## Declare a catkin package
catkin_package()

## Build talker and listener
include_directories(include ${catkin_INCLUDE_DIRS})
include_directories(  ${catkin_INCLUDE_DIRS}  ${OpenCV_INCLUDE_DIRS} )

add_executable(min_img_node src/min_img_node.cpp)
target_link_libraries(min_img_node ${OpenCV_LIBRARIES} ${catkin_LIBRARIES})
add_dependencies(min_img_node homework4_generate_messages_cpp)

# %EndTag(FULLTEXT)%
