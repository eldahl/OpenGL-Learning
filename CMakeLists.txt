cmake_minimum_required(VERSION 3.30)

project(opengl-learning)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

find_package(glfw3 3.4 REQUIRED)

# GLAD files
include_directories(${CMAKE_CURRENT_SOURCE_DIR}/glad/include)
file(GLOB BUTTERFLIES_SOURCES_C ${CMAKE_CURRENT_SOURCE_DIR} *.c glad/src/glad.c)
set(GLAD_SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/glad/src/glad.c)

add_executable(${PROJECT_NAME} main.cpp ${GLAD_SOURCES})

# GLFW
target_link_libraries(${PROJECT_NAME} glfw)

