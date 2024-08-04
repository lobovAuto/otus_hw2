cmake_minimum_required(VERSION 3.22)
project(homework2)


enable_language(CXX)

set (TARGET ip_filter)

add_executable(${TARGET} 
    ip_filter.cpp
)
target_include_directories(${TARGET} PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}
)

