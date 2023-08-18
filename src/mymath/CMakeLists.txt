# 子项目的CMakeLists
add_library(mymath mymath.cpp)

# 暴露库的头文件路径
target_include_directories(mymath PUBLIC ${CMAKE_CURRENT_SOURCE_DIR})
