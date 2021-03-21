cmake_minimum_required(VERSION 3.16)

project(main)

add_executable(main main.cpp)
target_compile_options(main PRIVATE -fprofile-arcs -ftest-coverage)
target_link_options(main PRIVATE --coverage)

install(TARGETS main)

enable_testing()
add_test(NAME main COMMAND main)
