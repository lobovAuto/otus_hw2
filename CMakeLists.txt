cmake_minimum_required(VERSION 3.22)
project(homework2)

if(DEFINED ENV{GITHUB_RUN_NUMBER})
  set(CMAKE_BUILD_NUMBER $ENV{GITHUB_RUN_NUMBER})
else()
  set(CMAKE_BUILD_NUMBER 0)
endif()


enable_language(CXX)

set (TARGET ip_filter)

add_executable(${TARGET} 
    ip_filter.cpp
)
target_include_directories(${TARGET} PRIVATE
    ${CMAKE_CURRENT_BINARY_DIR}
)

install(TARGETS ${TARGET} RUNTIME DESTINATION bin)

set(CPACK_GENERATOR DEB)
set(CPACK_PACKAGE_VERSION_MAJOR "${CMAKE_BUILD_NUMBER}")
set(CPACK_PACKAGE_VERSION_MINOR "${PROJECT_VERSION_MINOR}")
set(CPACK_PACKAGE_VERSION_PATCH "${PROJECT_VERSION_PATCH}")

set(CPACK_PACKAGE_CONTACT example@example.com)

include(CPack)
