cmake_minimum_required(VERSION 3.5)
project(TinyNTPClient)

add_library(TinyNTPClient INTERFACE)

target_include_directories(TinyNTPClient INTERFACE
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src>
    $<INSTALL_INTERFACE:include>
)

add_subdirectory(examples/ntp-desktop)