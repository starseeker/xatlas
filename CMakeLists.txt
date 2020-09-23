cmake_minimum_required(VERSION 3.1)

if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Build type")
    message(STATUS "No build type selected, default to ${CMAKE_BUILD_TYPE}")
endif()

project(xatlas)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")

set(xatlas_SOURCES xatlas.h xatlas.cpp)
add_library(xatlas STATIC ${xatlas_SOURCES})
