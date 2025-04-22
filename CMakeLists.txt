cmake_minimum_required(VERSION 3.28)
project(learnopengl)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include(FetchContent)

FetchContent_Declare(
  glfw
  GIT_REPOSITORY https://github.com/glfw/glfw.git
  GIT_TAG        3.4
)
FetchContent_MakeAvailable(glfw)

find_package(OpenGL)

add_library(glad src/glad.c)
target_include_directories(glad PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)

add_executable(OpenGLWindow src/main.cpp)
target_include_directories(OpenGLWindow PUBLIC ${CMAKE_CURRENT_LIST_DIR}/include)

target_link_libraries(OpenGLWindow PRIVATE glfw glad dl)
