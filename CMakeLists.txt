cmake_minimum_required( VERSION 3.5 )

project(3dcube C)

find_package( OpenGL REQUIRED )

include_directories( ${OPENGL_INCLUDE_DIRS} )

set( GLFW_BUILD_DOCS OFF CACHE BOOL  "GLFW lib only" )
set( GLFW_INSTALL OFF CACHE BOOL  "GLFW lib only" )
set( GLAD_GL "" )

add_subdirectory( lib/glfw )

file(GLOB ALL_SRCS 
  "${PROJECT_SOURCE_DIR}/inc/*.h"
  "${PROJECT_SOURCE_DIR}/src/*.c"
)

add_executable(3dcube ${ALL_SRCS})

target_link_libraries( 3dcube ${OPENGL_LIBRARIES} glfw )


