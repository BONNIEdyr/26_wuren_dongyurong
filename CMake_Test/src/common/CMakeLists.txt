#这里真的没有搞错吗common文件夹下没有include文件啊
set(Common_INCLUDE_DIRS ${CMAKE_CURRENT_LIST_DIR}/include CACHE PATH "Common_INCLUDE_DIRS")

execute_process(COMMAND ls ${CMAKE_CURRENT_SOURCE_DIR} OUTPUT_VARIABLE TEST_MODULE_COMMON_ST)
string(REPLACE "\n" ";" TEST_MODULE_COMMON_ST "${TEST_MODULE_COMMON_ST}")
foreach(m ${TEST_MODULE_COMMON_ST})
    if(IS_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR}/${m})
        if(EXISTS ${CMAKE_CURRENT_SOURCE_DIR}/${m}/CMakeLists.txt)
            add_subdirectory(${m})
        endif()
    endif()
endforeach()

