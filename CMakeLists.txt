cmake_minimum_required(VERSION 3.6)
project (Hello VERSION 0.0.1)

if (MSVC)
    SET(CMAKE_C_COMPILER C:/MinGW/bin/gcc)
    SET(CMAKE_CXX_COMPILER C:/MinGW/bin/g++)
endif(MSVC)

if(APPLE)
    SET(CMAKE_C_COMPILER /usr/bin/gcc)
    SET(CMAKE_CXX_COMPILER /usr/bin/g++)
endif(APPLE)

add_library(say-hello #SHARED
            hello.hpp
            hello.cpp)

add_executable(hello-cmake main.cpp)

target_link_libraries(hello-cmake PRIVATE say-hello)