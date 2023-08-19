cmake_minimum_required(VERSION 3.22.1)
project(HelloWorld)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_SOURCE_DIR ./src/)

add_subdirectory(./lib/mymath)

file(GLOB SRC_FILES ${CMAKE_SOURCE_DIR}/*.cpp)
enable_testing()
add_test(test_demo HelloWorld)
add_executable(HelloWorld ${SRC_FILES})
target_include_directories(HelloWorld PRIVATE include)
target_link_libraries(HelloWorld  mymath)
set_tests_properties(test_demo PROPERTIES PASS_REGULAR_EXPRESSION "hello world\n")
