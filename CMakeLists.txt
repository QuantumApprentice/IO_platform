cmake_minimum_required(VERSION 3.20)

project(IO_platform LANGUAGES CXX)

add_library(IO_platform STATIC
  io_Platform.cpp
)

add_library(IO_platform::IO_platform ALIAS IO_platform)

target_compile_features(IO_platform PUBLIC cxx_std_17)

target_include_directories(IO_platform
  PUBLIC
    "${CMAKE_CURRENT_SOURCE_DIR}"
)

target_compile_definitions(IO_platform
  PUBLIC
    $<$<PLATFORM_ID:Windows>:WINDOWS>
    $<$<PLATFORM_ID:Linux>:LINUX>
)
