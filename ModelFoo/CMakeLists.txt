cmake_minimum_required(VERSION 3.19)
set(PROJECT_NAME "Foo")
set(CXX_STANDARD 17)
set(CMAKE_BUILD_TYPE Release)
project(${PROJECT_NAME})


include_directories("include")


set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/libs)

#dll executable library
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/libs)

#static library
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/libs)

#add static library
add_library(${PROJECT_NAME}_static STATIC foo.cpp)

#add dynamic library
add_library(${PROJECT_NAME}_shared SHARED foo.cpp)
