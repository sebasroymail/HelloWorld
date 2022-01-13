cmake_minimum_required(VERSION 3.0.0)
project(HelloWorld VERSION 0.1.0)

include(CTest)
enable_testing()

# Name of C compiler.
set(CMAKE_C_COMPILER "/usr/bin/aarch64-linux-gnu-gcc-8")
set(CMAKE_CXX_COMPILER "/usr/bin/aarch64-linux-gnu-g++-8")

# Where to look for the target environment. (More paths can be added here)
set(CMAKE_FIND_ROOT_PATH /usr/aarch64-linux-gnu)
set(CMAKE_INCLUDE_PATH  /usr/include/aarch64-linux-gnu)
set(CMAKE_LIBRARY_PATH  /usr/lib/aarch64-linux-gnu)
set(CMAKE_PROGRAM_PATH  /usr/bin/aarch64-linux-gnu)

add_executable(HelloWorld ./src/main.cpp)
install(TARGETS HelloWorld DESTINATION bin)
set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
