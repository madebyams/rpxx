cmake_minimum_required(VERSION 3.30)
include(pico_sdk_import.cmake)

project(HC-SR04)
pico_sdk_init()

include_directories(include)
add_subdirectory(src)