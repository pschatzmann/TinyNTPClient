cmake_minimum_required(VERSION 3.5)
project(ntp-desktop)

# Fetch Arduino-Emulator
include(FetchContent)
FetchContent_Declare(
    arduino_emulator
    GIT_REPOSITORY https://github.com/pschatzmann/arduino-emulator.git
    GIT_TAG        main
)
FetchContent_MakeAvailable(arduino_emulator)

# ntp-desktop executable
add_executable(ntp-desktop ntp-desktop.cpp)
target_link_libraries(ntp-desktop PUBLIC TinyNTPClient arduino_emulator)
