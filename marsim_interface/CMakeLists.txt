cmake_minimum_required(VERSION 2.8.3)
project(marsim_interface)

find_package(catkin REQUIRED COMPONENTS quadrotor_msgs roscpp std_msgs
                                        geometry_msgs)

catkin_package(
  # INCLUDE_DIRS include LIBRARIES keyboard_interface CATKIN_DEPENDS
  # quadrotor_msgs roscpp std_msgs uav_utils DEPENDS system_lib
)

include_directories(include ${catkin_INCLUDE_DIRS})

add_executable(${PROJECT_NAME}_node src/${PROJECT_NAME}_node.cpp)
target_link_libraries(${PROJECT_NAME}_node ${catkin_LIBRARIES})
