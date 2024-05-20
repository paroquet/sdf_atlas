cmake_minimum_required(VERSION 3.10)

project(sdf_atlas VERSION 1.0)

set(CMAKE_CXX_STANDARD 14)
set(CMAKE_CXX_STANDARD_REQUIRED True)

set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -O2 -DNDEBUG")

include_directories(
        /opt/homebrew/Cellar/glfw/3.4/include
        /opt/homebrew/Cellar/glew/2.2.0_1/include
)

link_directories(
        /opt/homebrew/Cellar/glew/2.2.0_1/lib
        /opt/homebrew/Cellar/glfw/3.4/lib
)

set(SOURCES
        src/gl_utils.cpp
        src/parabola.cpp
        src/args_parser.cpp
        src/sdf_gl.cpp
        src/glyph_painter.cpp
        src/sdf_atlas.cpp
        src/font.cpp
        src/main.cpp
)

add_executable(sdf_atlas ${SOURCES})

target_link_libraries(sdf_atlas
        GLEW
        glfw
        "-framework OpenGL"
)
