# The Stick's firmware: ESP-IDF 5.x, with M5Unified for the screen, the
# buttons and the power.
#
#   idf.py set-target esp32      a StickC Plus2
#   idf.py set-target esp32s3    a StickS3
#   idf.py build flash monitor
cmake_minimum_required(VERSION 3.16)
include($ENV{IDF_PATH}/tools/cmake/project.cmake)
# What ESP-IDF 6 needs said that ESP-IDF 5 did without being asked
# (sdkconfig.defaults.idf6). A build given its own SDKCONFIG_DEFAULTS keeps them.
if(IDF_VERSION_MAJOR GREATER_EQUAL 6 AND NOT DEFINED SDKCONFIG_DEFAULTS
   AND NOT DEFINED ENV{SDKCONFIG_DEFAULTS})
    set(SDKCONFIG_DEFAULTS "sdkconfig.defaults;sdkconfig.defaults.idf6")
endif()
project(nesp32)
