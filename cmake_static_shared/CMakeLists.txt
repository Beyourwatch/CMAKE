cmake_minimum_required(VERSION 3.10)

project (hellocmake LANGUAGES CXX)

add_library(hellolib SHARED hello.cpp)

add_executable(hello main.cpp)

target_link_libraries(hello PUBLIC hellolib)
