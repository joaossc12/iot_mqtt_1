# Generated Cmake Pico project file

cmake_minimum_required(VERSION 3.13)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Initialise pico_sdk from installed location
# (note this can come from environment, CMake cache etc)

set(PICO_BOARD pico_w CACHE STRING "Board type")

# Pull in Raspberry Pi Pico SDK (must be before project)
include(pico_sdk_import.cmake)

project(iot_mqtt_1 C CXX ASM)

# Initialise the Raspberry Pi Pico SDK
pico_sdk_init()

# Add executable. Default name is the project name, version 0.1

add_executable(iot_mqtt_1 iot_mqtt_1.c lib/ssd1306.c)

pico_set_program_name(iot_mqtt_1 "iot_mqtt_1")
pico_set_program_version(iot_mqtt_1 "0.1")

# Modify the below lines to enable/disable output over UART/USB
pico_enable_stdio_uart(iot_mqtt_1 0)
pico_enable_stdio_usb(iot_mqtt_1 1)

# Add the standard library to the build
target_link_libraries(iot_mqtt_1
        pico_stdlib
        hardware_adc
        hardware_i2c
        pico_cyw43_arch_lwip_threadsafe_background
        pico_lwip_mqtt
        pico_mbedtls
        pico_lwip_mbedtls)

# Add the standard include files to the build
target_include_directories(iot_mqtt_1 PRIVATE
        ${CMAKE_CURRENT_LIST_DIR}
)

# Add any user requested libraries
target_link_libraries(iot_mqtt_1 
        
        )

pico_add_extra_outputs(iot_mqtt_1)

