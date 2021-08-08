cmake_minimum_required(VERSION 3.13.4)

project(tamachan)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

find_package(Boost 1.72.0 REQUIRED COMPONENTS thread)
if(Boost_FOUND)
    message(STATUS "Boost version: ${Boost_VERSION}")
    include_directories(${Boost_INCLUDE_DIRS})
    add_executable(tamachan tamachan.cpp)
    target_link_libraries(tamachan ${Boost_LIBRARIES})
endif()
