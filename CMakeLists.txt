#cmake ver req
cmake_minimum_required(VERSION 2.6)

set(project_name smaa)

#project name
project(${project_name})

#so that it talks to us
set(CMAKE_VERBOSE_MAKEFILE ON)
#add_definitions( "-Wall -Wno-long-long -ansi -pedantic" )

#header files source
include_directories(${CMAKE_SOURCE_DIR}/src/)
link_directories(${CMAKE_SOURCE_DIR}/src/)

include_directories(${CMAKE_SOURCE_DIR}/external/include/)
link_directories(${CMAKE_SOURCE_DIR}/external/lib/)

set(${project_name}_external_libs sfml-window sfml-system sfml-audio GLEW GL)

#adding the project's exe
add_executable(${project_name} main)

target_link_libraries(${project_name} ${${project_name}_external_libs})