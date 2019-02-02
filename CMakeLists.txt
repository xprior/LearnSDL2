cmake_minimum_required (VERSION 3.10.2)

project(LearnSDL)
set(LearnSDL_VERSION_MAJOR 1)
set(LearnSDL_VERSION_MINOR 0)
set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} "${CMAKE_SOURCE_DIR}/cmake/") #How can i see variables at run-time?

#add_subdirectory(src)

find_package(SDL2 REQUIRED)

add_executable(01_hello src/01_hello_SDL.cpp)

#include_directories() works for all targets being built by cmake

#target_include_directories(01_hello PUBLIC ${SDL2_INCLUDE_DIRS}) This specifies where to look for the include files, 
# but this file is in /usr/include/SDL2 which is part of the default search, same for intelissense.
target_link_libraries(01_hello ${SDL2_LIBRARIES})