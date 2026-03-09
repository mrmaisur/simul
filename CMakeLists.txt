cmake_minimum_required(VERSION 3.20)

project(OpenGLPlayground LANGUAGES C CXX)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

find_package(OpenGL REQUIRED)
find_package(glfw3 REQUIRED)
find_package(glm REQUIRED)

add_subdirectory(external/glad)

add_executable(app
    src/main.cpp
)

target_link_libraries(app
    glfw
    OpenGL::GL
    glad
    glm::glm
)

target_compile_options(app PRIVATE
    -Wall
    -Wextra
    -Wpedantic
)