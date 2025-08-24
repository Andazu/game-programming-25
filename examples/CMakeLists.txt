cmake_minimum_required(VERSION 3.25)
project(game_programming_examples C CXX)

set(CMAKE_C_STANDARD 11)
set(CMAKE_CXX_STANDARD 17)

# Help CMake find MSYS2 packages
# (you can also pass this as a CMake option in CLion instead of hardcoding)
set(CMAKE_PREFIX_PATH "C:/msys64/mingw64")

# Find SDL3 package provided by MSYS2
find_package(SDL3 CONFIG REQUIRED)

# Example 0 and 1 don't need SDL
add_executable(00_hello_world 00_hello_world.c)
add_executable(01_hello_world 01_hello_world.cpp)

# Example 2 needs SDL3
add_executable(02_hello_sdl 02_hello_sdl.cpp)
target_link_libraries(02_hello_sdl PRIVATE SDL3::SDL3)
