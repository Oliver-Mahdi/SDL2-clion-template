cmake_minimum_required(VERSION 3.22)
project(secret-project)

set(CMAKE_CXX_STANDARD 14)

# Must set the path to the main.cpp, for example: scripts/main.cpp if it is inside a folder
add_executable(${PROJECT_NAME} scripts/main.c)

# --- SDL2 SETUP ---
set(CMAKE_MODULE_PATH ${CMAKE_SOURCE_DIR}/cmake/modules)
set(SDL2_PATH "SDL2/x86_64-w64-mingw32")

find_package(SDL2 REQUIRED)
include_directories(${SDL2_INCLUDE_DIR})

set(SDL2_IMAGE_PATH "SDL2/x86_64-w64-mingw32")
find_package(SDL2_image REQUIRED)

set(SDL2_MIXER_PATH "SDL2/x86_64-w64-mingw32")
find_package(SDL2_mixer REQUIRED)


target_link_libraries(${PROJECT_NAME} ${SDL2_LIBRARY})