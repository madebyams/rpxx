add_library(ST7789
    ST7789_SPI.cc
    ST7789.cc
)

target_link_libraries(ST7789
    PRIVATE
    pico_stdlib
    hardware_spi
)