project(CmakeTest)
cmake_minimum_required(VERSION 3.1)

set(CMAKE_MAKE_PROGRAM "E:/MinGW64/mingw64/bin/make.exe")
set(CMAKE_C_COMPILER "E:/MinGW64/mingw64/bin/gcc.exe")
set(CMAKE_CXX_COMPILER "E:/MinGW64/mingw64/bin/g++.exe")

# ${PROJECT_SOUCE_DIR}为包含project命令的最近一个CMakeLists.txt所在文件夹
include_directories(${PROJECT_SOUCE_DIR}/src)  # 需要include的东西 .h 所在位置


# a.编译可执行文件
set(EXECUTABLE_OUTPUT_PATH ${PROJECT_SOURCE_DIR}/bin/${PLATFORM})   # 设置最终可执行文件的输出位置
add_executable(test ${PROJECT_SOURCE_DIR}/src/test.cpp)             # 编译时将输出一个可执行文件：json_test

# b.编译库
# set(LIBRARY_OUT_PATH ${PROJECT_SOURCE_DIR}/bin/${PLATFORM})       # 设置编译得到的库的位置
# add_library(jsoncpp STATIC ${SOURCE_Files})                       # 编译时将输出一个Static库：jsoncpp


# 告诉链接器在哪里查找库
# link_directories(${PROJECT_SOURCE_DIR}/3rd/)

# 执行链接：使json_test能够用到jsoncpp库的东西
# target_link_libraries(json_test jsoncpp)
