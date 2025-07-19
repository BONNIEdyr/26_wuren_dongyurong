#下面主要是复制kalman中的cmakelists来的
# 查找OpenCV包
find_package(OpenCV REQUIRED)

# 定义math头文件目录
set(math_INCLUDE_DIR)
list(APPEND math_INCLUDE_DIR "${CMAKE_CURRENT_LIST_DIR}/include")
list(APPEND math_INCLUDE_DIR "${OpenCV_INCLUDE_DIRS}")

set(math_INCLUDE_DIRS ${math_INCLUDE_DIR}
                        CACHE PATH "math filter include directories")

# 添加math源文件
set(MATH_SRC
    src/Math.cpp
)

# 创建静态库
add_library(Math STATIC ${MATH_SRC})

# 给math库添加头文件搜索路径
target_include_directories(Math PUBLIC ${math_INCLUDE_DIRS})

# 链接OpenCV库到math库
target_link_libraries(Math PUBLIC ${OpenCV_LIBS})

