find_package(OpenCV REQUIRED)
include_directories( ${OpenCV_INCLUDE_DIRS} )

set(kalman_INCLUDE_DIR)
list(APPEND kalman_INCLUDE_DIR "${CMAKE_CURRENT_LIST_DIR}/include")
list(APPEND kalman_INCLUDE_DIR "${OpenCV_INCLUDE_DIRS}")

set(kalman_INCLUDE_DIRS ${kalman_INCLUDE_DIR}
                        CACHE PATH "kalman filter include directories")
#由于没有源文件，不需要创建库只需要创建接口即可
add_library(kalman INTERFACE) 
#给kalman接口添加头文件搜索路径
target_include_directories(kalman INTERFACE ${kalman_INCLUDE_DIRS}) 
