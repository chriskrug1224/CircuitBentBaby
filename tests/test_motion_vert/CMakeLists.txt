cmake_minimum_required(VERSION 3.13)

# initialize the SDK based on PICO_SDK_PATH
# note: this must happen before project()
include(pico_sdk_import.cmake)
include(pico_extras_import.cmake)

project(my_project)

# initialize the Raspberry Pi Pico SDK
pico_sdk_init()

# rest of your project
add_executable(test_motion_vert
    test_motion_vert.c
)

# Add pico_stdlib library which aggregates commonly used features
target_link_libraries(test_motion_vert pico_multicore pico_stdlib pico_scanvideo_dpi)

# create map/bin/hex/uf2 file in addition to ELF.
pico_add_extra_outputs(test_motion_vert)
