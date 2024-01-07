cmake_minimum_required(VERSION 2.8.3)
project(marsim_simulator)

add_compile_options(-std=c++14)

find_package(catkin REQUIRED COMPONENTS nav_msgs roscpp std_msgs)

find_package(Eigen3 REQUIRED)
add_definitions(${EIGEN_DEFINITIONS})

catkin_package(
  INCLUDE_DIRS
  include
  # LIBRARIES mars_drone_sim
  CATKIN_DEPENDS
  nav_msgs
  roscpp
  std_msgs
  DEPENDS
  system_lib)

include_directories(include ${catkin_INCLUDE_DIRS} ${EIGEN3_INCLUDE_DIR})

add_executable(quadrotor_dynamics_node src/quadrotor_dynamics_node.cpp)
target_link_libraries(quadrotor_dynamics_node ${catkin_LIBRARIES})
