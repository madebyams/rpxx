add_library(HC-SR04
    HC-SR04.cc
)

target_link_libraries(HC-SR04
    PRIVATE
    pico_stdlib
)