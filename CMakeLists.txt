cmake_minimum_required(VERSION 3.5)

project(06.homework)

add_executable(container src/main.cpp)

target_include_directories(container PRIVATE include)
target_include_directories(container PRIVATE src)
set_target_properties(container PROPERTIES CXX_STANDARD 17 CXX_STANDARD_REQUIRED ON)


if (CMAKE_CXX_COMPILER_ID MATCHES "Clang" OR
    CMAKE_CXX_COMPILER_ID STREQUAL "GNU")
    target_compile_options(container PRIVATE 
        -g
        -Wall
        -Wextra
        -Werror
        -pedantic
    )
elseif (CMAKE_CXX_COMPILER_ID STREQUAL "MSVC")
    target_compile_options(container PRIVATE
        /EHsc
        /W4
        /WX
    )
endif()