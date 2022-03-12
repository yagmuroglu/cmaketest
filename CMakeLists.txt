cmake_minimum_required(VERSION 3.6)
project (Hello VERSION 0.0.1)

add_library(say-hello #SHARED
            hello.hpp
            hello.cpp)

add_executable(hello-cmake main.cpp)

target_link_libraries(hello-cmake PRIVATE say-hello)