cmake_minimum_required(VERSION 3.1)

project(XATLAS)

set(CMAKE_CXX_STANDARD 14)

set(xatlas_SOURCES xatlas.h xatlas_c.h xatlas.cpp)
add_library(xatlas SHARED ${xatlas_SOURCES})
set_property(TARGET xatlas APPEND PROPERTY COMPILE_DEFINITIONS "XATLAS_EXPORTS")
set_property(TARGET xatlas APPEND PROPERTY INTERFACE_COMPILE_DEFINITIONS "XATLAS_IMPORTS")

add_subdirectory(examples)
add_subdirectory(tests)
