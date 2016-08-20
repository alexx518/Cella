cmake_minimum_required(VERSION 2.8)
project(cella)

set(SRC_DIR    ${CMAKE_SOURCE_DIR}/src)

set(CMAKE_CXX_FLAGS "-std=c++11 -Wall -Wextra")

# fltk
find_package(FLTK REQUIRED NO_MODULE)
include_directories(${FLTK_INCLUDE_DIR})

# source files
set(SRC         ${SRC_DIR}/main.cpp
				${SRC_DIR}/cella.cpp)

# create executable and link fltk library
add_executable(${PROJECT_NAME} ${SRC})
target_link_libraries(${PROJECT_NAME} fltk_SHARED)

target_link_libraries(${PROJECT_NAME} -pthread)
