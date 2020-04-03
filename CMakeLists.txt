cmake_minimum_required(VERSION 3.17.0)

project(snake)

add_executable(snake main.cpp)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

target_compile_options(snake PRIVATE -Werror)

target_compile_features(snake PRIVATE cxx_std_17)

# Find SFML
find_package(SFML 2.5 COMPONENTS audio graphics window system REQUIRED)

#Include SOL2 header files
include_directories(${CMAKE_SOURCE_DIR}/sol2/include)

#add_subdirectory(ECS)

target_link_libraries(snake
        PUBLIC
        sfml-graphics sfml-audio sfml-window sfml-system )
