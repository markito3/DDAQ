cmake_minimum_required(VERSION 3.0)

# set the project name
project(DDAQ)

# specify the C++ standard
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

file(GLOB SOURCES src/*.cc)
add_library(DDAQ STATIC ${SOURCES})
include_directories(${CMAKE_SOURCE_DIR}/include $ENV{JANA_HOME}/include $ENV{ROOTSYS}/include $ENV{LIBHDDM_HOME}/include $ENV{HDDM_HOME}/include)
install(
  TARGETS DDAQ
  DESTINATION lib
  )
