cmake_minimum_required(VERSION 3.13)

include(pico_sdk_import.cmake)

project(midi_adaptor C CXX ASM)
set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

pico_sdk_init()

add_executable(midi_adaptor
  main.c
  usb_descriptors.c
)

# Example source
target_sources(midi_adaptor PRIVATE
        main.c
        usb_descriptors.c
        )

# Example include
target_include_directories(midi_adaptor PRIVATE
        ${CMAKE_CURRENT_SOURCE_DIR}
        )
target_link_libraries(midi_adaptor PRIVATE pico_stdlib hardware_pio hardware_adc hardware_pwm tinyusb_device tinyusb_board)

pico_add_extra_outputs(midi_adaptor)
