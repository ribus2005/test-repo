cmake_minimum_required(VERSION 3.24.2)
project(testproj CXX)

include_directories(./)
add_executable(${PROJECT_NAME} main.cpp candle.cpp)
