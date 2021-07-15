cmake_minimum_required(VERSION 3.1)

project(XATLAS)

add_definitions(-g)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++14")
if (CMAKE_CXX_COMPILER_VERSION VERSION_LESS 7.0)
    # avoid the "‘nodiscard’ attribute directive ignored" warning
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wno-attributes")
endif()

set(xatlas_SOURCES xatlas.h xatlas_c.h xatlas.cpp)
add_library(xatlas SHARED ${xatlas_SOURCES})

add_subdirectory(examples)
add_subdirectory(tests)
