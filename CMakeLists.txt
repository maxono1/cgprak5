cmake_minimum_required(VERSION 3.20)
project(clion)

set(CMAKE_CXX_STANDARD 14)

file(GLOB SOURCES
        *.h
        *.cpp
        )

add_executable(ClionProject ${SOURCE_FILES} ${SOURCES})

include_directories(
        libraries/glfw/include
        libraries/glew/include
        libraries/freeimage/include
        libraries/assimp/include)

find_package(OpenGL REQUIRED)

target_link_libraries(ClionProject
        OpenGL::GL
        OpenGL::GLU
        ../libraries/glfw/lib/glfw3
        ../libraries/glew/lib/glew32
        ../libraries/freeimage/lib/FreeImage
        ../libraries/assimp/lib/assimp-vc140-mt)