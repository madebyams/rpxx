add_library(SSD1306
    SSD1306.cc
    SSD1306_I2C.cc
    Fonts/Fonts.cc
)

target_link_libraries(SSD1306
    PRIVATE
    pico_stdlib
    hardware_i2c
)