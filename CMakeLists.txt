# Set min req version of Cmake
cmake_minimum_required(VERSION 3.13)

# Set project name
project(SeggerRTT_lib)

# Set our lib include directories
include_directories(RTT)

# Set the lib output folder
set(CMAKE_ARCHIVE_OUTPUT_DIRECTORY ../lib)

# Create or our static library
add_library(seggerRTT STATIC RTT/SEGGER_RTT.c RTT/SEGGER_RTT_printf.c)