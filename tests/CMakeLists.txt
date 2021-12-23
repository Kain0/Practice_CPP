cmake_minimum_required(VERSION 3.20)
project(Test_BigInteger)
set(CMAKE_CXX_STANDARD 20)

add_subdirectory(lib/googletest-main)
include_directories(lib/googletest-main/googletest/include)
include_directories(lib/googletest-main/googlemock/include)

add_executable(Test_BigInteger Test_BigInteger.cpp)

target_link_libraries(Test_BigInteger gtest gtest_main)

add_test(
        NAME Test_BigInteger
        COMMAND $<TARGET_FILE:${Test_BigInteger}> --gtest_output=xml:${CMAKE_BINARY_DIR}/test_results/Test_BigInteger.xml
)