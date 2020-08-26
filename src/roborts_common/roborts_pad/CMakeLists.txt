cmake_minimum_required(VERSION 2.8.3)
project(roborts_pad)

find_package(catkin REQUIRED COMPONENTS 
    message_generation
    robotnik_msgs
    roscpp 
    sensor_msgs 
    geometry_msgs 
    diagnostic_updater
    )
    
add_service_files(DIRECTORY srv 
   FILES
    enable_disable_pad.srv
)

generate_messages(
   DEPENDENCIES
   robotnik_msgs sensor_msgs roborts_pad
 )

catkin_package(
  CATKIN_DEPENDS 
    robotnik_msgs
    roscpp 
    sensor_msgs 
    geometry_msgs 
    message_runtime
)

include_directories(
  include 
  ${catkin_INCLUDE_DIRS} 
)

add_executable(roborts_pad src/roborts_pad.cpp)

add_dependencies(roborts_pad roborts_pad_generate_messages_cpp)

target_link_libraries(roborts_pad
   ${catkin_LIBRARIES}
 )

install(
  TARGETS roborts_pad
  DESTINATION ${CATKIN_PACKAGE_BIN_DESTINATION}
)

install(
  DIRECTORY launch config
  DESTINATION ${CATKIN_PACKAGE_SHARE_DESTINATION}
)
