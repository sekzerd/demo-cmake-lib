cmake_minimum_required(VERSION 3.19)
set(PROJECT_NAME "LibDemo")
set(CXX_STANDARD 17)
project(${PROJECT_NAME})
set(CMAKE_BUILD_TYPE Release)


include_directories("ModelFoo/include")
link_directories("ModelFoo/libs")


set(CMAKE_LIBRARY_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

#dll executable library
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

#static library
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/bin)

add_executable(${PROJECT_NAME}_static main.cpp)
target_link_libraries(${PROJECT_NAME}_static Foo_static)

add_executable(${PROJECT_NAME}_shared main.cpp)
target_link_libraries(${PROJECT_NAME}_shared Foo_shared)


