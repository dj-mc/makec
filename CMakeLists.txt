cmake_minimum_required(VERSION 3.7...3.22)

if(${CMAKE_VERSION} VERSION_LESS 3.12)
    cmake_policy(VERSION ${CMAKE_MAJOR_VERSION}.${CMAKE_MINOR_VERSION})
endif()

project(
    makec
    VERSION 1.0
    DESCRIPTION "makec"

    # Supported languages:
    # C, CXX, Fortran, ASM, Cuda, C#, Swift
    LANGUAGES CXX
)

add_executable(built_exe init.cpp)
add_library(lib_name library.cpp library.hpp)
target_link_libraries(built_exe PRIVATE lib_name)

enable_testing()
add_test(NAME built_exe COMMAND built_exe)
