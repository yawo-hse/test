cmake_minimum_required(VERSION 3.5)

if (CMAKE_COMPILER_IS_GNUCC)
   option(ENABLE_COVERAGE "Enable cover reporting for gcc/clang" FALSE)
   if(ENABLE_COVERAGE)
       add_compile_options(--coverage -00)
   endif()
   

add_executable(intro main.cpp)
target_link_libraries(intro --coverage)

enable_testing()

add_executable(tester tester.cpp)
target_link_libraries(tester --coverage)
add_test(Tester tester)
