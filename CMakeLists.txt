cmake_minimum_required(VERSION 3.22.1)
project(HelloWorld)
include(CTest)
set(CMAKE_CXX_STANDARD 20)
set(CMAKE_SOURCE_DIR ./src/)


set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${BINARY_DIR})
add_subdirectory(./lib/mymath)

file(GLOB SRC_FILES ${CMAKE_SOURCE_DIR}/*.cpp)
add_test(HelloWorld ${BINARY_DIR}/HelloWorld)
add_executable(HelloWorld ${SRC_FILES})
target_include_directories(HelloWorld PRIVATE include)
target_link_libraries(HelloWorld  mymath)