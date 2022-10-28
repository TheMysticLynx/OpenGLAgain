cmake_minimum_required(VERSION 3.23)
project(OpenGLAgain)

set(CMAKE_CXX_STANDARD 14)

set(GLFW_BUILD_DOCS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_TESTS OFF CACHE BOOL "" FORCE)
set(GLFW_BUILD_EXAMPLES OFF CACHE BOOL "" FORCE)

add_subdirectory(Lib/glfw-3-3-8)

add_executable(Main src/main.cpp src/Classes/glad.c)

target_link_libraries(Main glfw)
target_include_directories(Main PRIVATE Lib/glfw-3-3-8/include)

find_package(OpenGL REQUIRED)
target_include_directories(Main PRIVATE Lib/glad/include )

target_link_libraries(Main OpenGL::GL)