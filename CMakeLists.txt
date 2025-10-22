cmake_minimum_required(VERSION 3.21)
project(First_Steps CXX)
set(CMAKE_CXX_STANDARD 20)

find_package(glfw3 CONFIG REQUIRED)
find_package(glad CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)
find_package(OpenGL REQUIRED)

set(COMMON_SRC
)

add_executable(HelloTriangle
        src/HelloTriangle/main.cpp
        ${COMMON_SRC}
)

add_executable(HelloSquare
        src/HelloSquare/main.cpp
        ${COMMON_SRC}
)

set(OPENGL_DEPS
        glfw
        glad::glad
        glm::glm
        OpenGL::GL
)

target_link_libraries(HelloTriangle PRIVATE ${OPENGL_DEPS})
target_link_libraries(HelloSquare  PRIVATE ${OPENGL_DEPS})



