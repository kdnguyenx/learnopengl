cmake_minimum_required(VERSION 4.0)
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

add_executable(OpenGLWindow src/main.cpp)

target_include_directories(OpenGLWindow PRIVATE ${CMAKE_CURRENT_LIST_DIR}/include)
target_link_libraries(OpenGLWindow PRIVATE glfw)
