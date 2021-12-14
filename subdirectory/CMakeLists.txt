cmake_minimum_required(VERSION 3.10)

project(hello)

add_subdirectory(lib)

add_executable(hello main.cpp)

target_link_libraries(hello PRIVATE libhello)
target_include_directories(hello PRIVATE lib)


