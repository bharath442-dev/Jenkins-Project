cmake_minimum_required(VERSION 3.10)(VERSION 3.8)
set(This Example)

project(${This} C XX)

set(CMAKE_C_STADARD 99)
set(CMAKE_C_STANDARD 11)
set(CMAKE_POSITION_INDEPENDENT_CODE ON)

enable_testing()

add_subdirectory(googletest)

set(Headers
    Example.hpp
)
set(Sources
    Example.cpp
)

add_library(${This} STATIC ${Sources} ${Headers})
add_subdirectory(test)