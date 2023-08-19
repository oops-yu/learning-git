cmake_minimum_required(VERSION 3.22.1)
project(HelloWorld LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_SOURCE_DIR ./src/)
set(CMAKE_BINARY_DIR ./build)


find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)

add_subdirectory(./lib/imgui)
file(GLOB SRC_FILES ${CMAKE_SOURCE_DIR}/*.cpp)


add_executable(HelloWorld ${SRC_FILES})
target_link_libraries(HelloWorld imgui GL glfw)
target_include_directories(HelloWorld PRIVATE include)


