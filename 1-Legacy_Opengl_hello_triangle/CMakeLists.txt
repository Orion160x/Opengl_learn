﻿# CMakeList.txt : CMake project for Opengl_learn, include source and define
# project specific logic here.
#
cmake_minimum_required (VERSION 3.16)

# Set c++ standard and ensure compiler compability
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_EXTENSIONS OFF)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


# Configuring Project structure
set(SRC_DIR "src/")
set(INCLUDE_DIR "include/")

set(SRC "${SRC_DIR}lhello_triangle.cpp")
set(HEADERS "${INCLUDE_DIR}lhello_triangle.h")

# libraries to find
find_package(glad CONFIG REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
     

# Add source to this project's executable.
add_executable (lhello_triangle "${SRC}" "${HEADERS}")

target_include_directories(lhello_triangle PRIVATE ${INCLUDE_DIR})

target_link_libraries(lhello_triangle PRIVATE glad::glad)
target_link_libraries(lhello_triangle PRIVATE glfw)

# TODO: Add tests and install targets if needed.
