cmake_minimum_required(VERSION 3.24.2)
project(riba CXX)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_COMPILER "gcc")
include(FetchContent)
FetchContent_Declare(
  googletest
  URL https://github.com/google/googletest/archive/03597a01ee50ed33e9dfd640b249b4be3799d395.zip
)

set(gtest_force_shared_crt ON CACHE BOOL "" FORCE)
FetchContent_MakeAvailable(googletest)

enable_testing()

include_directories(./)
add_executable(riba main.cpp candle.cpp)

target_link_libraries(riba GTest::gtest_main)

include(GoogleTest)

gtest_discover_tests(riba)
