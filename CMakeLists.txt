cmake_minimum_required(VERSION 3.7)

project (SDL2-Pong)

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIR})


add_executable(pong ./src/pong.cpp ${SDL2_LIBRARY})
