cmake_minimum_required(VERSION 3.1)

if (NOT CMAKE_BUILD_TYPE)
    set(CMAKE_BUILD_TYPE "Release" CACHE STRING "Build type")
    message(STATUS "No build type selected, default to ${CMAKE_BUILD_TYPE}")
endif()

project(xatlas)

if (WIN32)
    # clang on windows uses visual studio standard library, which uses c++14 features
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14")
else()
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++11")
    if (CMAKE_CXX_COMPILER_VERSION VERSION_LESS 7.0)
        # avoid the "‘nodiscard’ attribute directive ignored" warning
        set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-attributes")
    endif()
endif()

set(xatlas_SOURCES xatlas.h xatlas.cpp)
add_library(xatlas STATIC ${xatlas_SOURCES})
