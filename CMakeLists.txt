cmake_minimum_required(VERSION 3.7)

project (SDL2-Pong)

if(WIN32)
  include_directories(${PROJECT_SOURCE_DIR}/extern/SDL2-2.0.9/include)
  link_directories(${PROJECT_SOURCE_DIR}/extern/SDL2-2.0.9/lib/x86)
  include_directories(${PROJECT_SOURCE_DIR}/extern/SDL2_image-2.0.4/include)
  link_directories(${PROJECT_SOURCE_DIR}/extern/SDL2_image-2.0.4/lib/x86)
  include_directories(${PROJECT_SOURCE_DIR}/extern/SDL2_ttf-2.0.15/include)
  link_directories(${PROJECT_SOURCE_DIR}/extern/SDL2_ttf-2.0.15/lib/x86)
  set(CMAKE_EXE_LINKER_FLAGS "${CMAKE_EXE_LINKER_FLAGS} /SUBSYSTEM:CONSOLE")
endif()

if(APPLE)
  include_directories(/usr/local/include)
  link_directories(/usr/local/lib)
endif()

add_executable(pong ./src/pong.cpp)
target_link_libraries(pong SDL2 SDL2_image SDL2_ttf)


