cmake_minimum_required(VERSION 2.8.3)
project(ros_odevler_ikinci_asama)


find_package(OpenCV REQUIRED)
find_package(catkin REQUIRED COMPONENTS
  sensor_msgs
  cv_bridge
  roscpp
  std_msgs
  image_transport
  OpenCV
)






catkin_package(
  INCLUDE_DIRS
  CATKIN_DEPENDS 
                sensor_msgs
                cv_bridge
                roscpp
                std_msgs
                image_transport                    
)
include_directories( ${catkin_INCLUDE_DIRS}
${OpenCV_INCLUDE_DIRS})

add_executable(image_subscriber src/image_subscriber.cpp)
target_link_libraries(image_subscriber ${catkin_LIBRARIES} ${OpenCV_LIBS})
