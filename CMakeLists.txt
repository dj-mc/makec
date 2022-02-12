cmake_minimum_required(VERSION 3.7...3.22)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

project(
    eg_project
    VERSION 1.0
    DESCRIPTION "Noice"

    # Supported languages:
    # C, CXX, Fortran, ASM, Cuda, C#, Swift
    LANGUAGES CXX
)

add_executable(my_exe eg.cpp)
add_library(my_lib eg_lib.cpp eg_lib.hpp)
target_link_libraries(my_exe PRIVATE my_lib)

enable_testing()
add_test(NAME my_exe COMMAND my_exe)
