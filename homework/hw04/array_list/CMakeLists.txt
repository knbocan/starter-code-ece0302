cmake_minimum_required(VERSION 3.5)
project(arraylist CXX)

# require a C++11 compiler for all targets
set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

set(SOURCE test_array_list.cpp array_list.hpp array_list.tpp)

add_executable(test_array_list catch.hpp ${SOURCE})

enable_testing()

add_test(test_array_list test_array_list)

add_custom_target(submission COMMAND
    ${CMAKE_COMMAND} -E tar "cfv" "${CMAKE_CURRENT_BINARY_DIR}/hw4_list_array.zip" --format=zip
       ${SOURCE}
       WORKING_DIRECTORY ${CMAKE_CURRENT_SOURCE_DIR})