cmake_minimum_required(VERSION 3.26.0)
project(cmake_test VERSION 1.0.0)
cmake_policy(SET CMP0072 NEW)

set(CMAKE_MODULE_PATH ${CMAKE_MODULE_PATH} ${CMAKE_CURRENT_SOURCE_DIR}/cmake)
set(GLFW3_LIBRARY "${CMAKE_SOURCE_DIR}/include/glfw/glfw3.lib")
find_package(OpenGL REQUIRED)

#find_package(glfw3 REQUIRED)

add_executable(cmake_test
    src/main.cpp
    src/glad.c
)

target_include_directories(cmake_test PRIVATE 
    ${CMAKE_SOURCE_DATA}/include
    ${CMAKE_SOURCE_DIR}/include
    ${CMAKE_SOURCE_DIR}/include/glfw/include
)

target_link_libraries(cmake_test PRIVATE OpenGL::GL "${CMAKE_SOURCE_DIR}/include/glfw/lib-vc2022/glfw3.lib")