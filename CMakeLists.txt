cmake_minimum_required(VERSION 3.19)
project(box2d-proof-of-concept)

set(CMAKE_CXX_STANDARD 17)

set(CMAKE_CURRENT_SOURCE_DIR .)

# create variable for source dir
set(BOX2D_SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/libraries/box2d)

# add subdirectory of the
add_subdirectory(${BOX2D_SOURCE_DIR} ${CMAKE_CURRENT_BINARY_DIR}/box2d)

add_executable(box2d-proof-of-concept main.cpp)

target_include_directories(box2d-proof-of-concept PUBLIC
        ${BOX2D_SOURCE_DIR}/include/box2d
        )

target_link_libraries(box2d-proof-of-concept box2d)