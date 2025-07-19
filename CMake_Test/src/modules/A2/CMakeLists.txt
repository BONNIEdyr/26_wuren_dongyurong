#编译源文件并且生成A2静态库
add_library(A2 STATIC src/A2.cpp)
# 编译A2源文件的时候cmake会从相对路径下include文件中找到头文件
target_include_directories(A2 PUBLIC include)
#没有依赖故不需要使用target_link_library命令
