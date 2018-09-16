cmake_minimum_required(VERSION 3.8)

project('sdnn')


file(GLOB_RECURSE sources
    "src/*.cpp"
    "src/*.cc"
    "include/*.hpp"
)

find_package(OpenCV)
if(NOT OpenCV_FOUND)
    message(FATAL_ERROR "not find opencv.")
endif()

add_executable(main main.cpp ${sources})
target_link_libraries(main ${sources} ${OpenCV_LBS})

