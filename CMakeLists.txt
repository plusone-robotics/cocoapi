cmake_minimum_required(VERSION 3.0.2)
project(cocoapi)

find_package(catkin REQUIRED COMPONENTS)

catkin_package(
  INCLUDE_DIRS common
  LIBRARIES ${PROJECT_NAME}
  CATKIN_DEPENDS
)

add_library(${PROJECT_NAME} SHARED
  common/maskApi.c
)

install(DIRECTORY common/
  DESTINATION ${CATKIN_PACKAGE_INCLUDE_DESTINATION}
)

install(TARGETS ${PROJECT_NAME}
  LIBRARY DESTINATION ${CATKIN_PACKAGE_LIB_DESTINATION}
)
