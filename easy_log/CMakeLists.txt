# 指定cmake版本
cmake_minimum_required(VERSION 3.0)
# 工程名
project(main)

#cmake的c++设置
# 告知當前使用的是交叉編譯方式，必須配置
# SET(CMAKE_SYSTEM_NAME Linux)
# SET(CMAKE_C_COMPILER "arm-linux-gnueabihf-gcc")
# SET(CMAKE_CXX_COMPILER "arm-linux-gnueabihf-g++")

# 设置编译选项
set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -O0 -Wall -pthread -std=c++11 -fPIC ")

# 添加.h文件
include_directories(include)

# 添加.cpp文件
aux_source_directory(src SRC_LIST)


# 输出调试信息
message("src :${SRC_LIST} ")

# 执行文件
add_executable(main ${SRC_LIST} )

