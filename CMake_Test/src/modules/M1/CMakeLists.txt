aux_source_directory(src Path_M1) # 将当前目录下的所有源文件的相对路径都保存到src变量中

add_library(M1 STATIC ${Path_M1})

target_include_directories(M1 PUBLIC include)
target_link_libraries(M1 PUBLIC A1)#添加生成库所需的依赖
