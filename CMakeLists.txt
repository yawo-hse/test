cmake_minimum_required(VERSION 3.16)

if (CMAKE_COMPILER_IS_GNUCC)
   option(ENABLE_COVERAGE "Enable cover reporting for gcc/clang" TRUE)
   if(ENABLE_COVERAGE)
       add_compile_options(--coverage -O0 -g)
   endif()
endif()

project(main)

add_executable(main main.cpp)

install(TARGETS main)

enable_testing()
add_test(NAME main COMMAND main)
