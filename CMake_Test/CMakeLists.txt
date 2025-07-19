
cmake_minimum_required(VERSION 3.10) #但是我环境配置的是4.+的
project(Test)
# 添加子模块，对子文件夹中的源文件进行编译,一开始这里路径没有写清楚
add_subdirectory(src/common)
add_subdirectory(src/modules)

set(CMAKE_CXX_STANDARD 14) #使用C++14标准进行编译,因为不使用就会报错
set(CMAKE_CXX_STANDARD_REQUIRED ON)

# 因为是最顶层的cmakelists所以不用生成库只需要生成可执行文件即可，test是根据作业要求添加的
add_executable(test src/main.cpp)

# 链接库,才能生成最终完整的可执行文件
target_link_libraries(test M1 M2 Math)


