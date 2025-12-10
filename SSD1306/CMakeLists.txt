cmake_minimum_required(VERSION 3.30)
include(pico_sdk_import.cmake)

project(SSD1306)
pico_sdk_init()

include_directories(include)
add_subdirectory(src)