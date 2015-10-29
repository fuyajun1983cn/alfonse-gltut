cmake_minimum_required(VERSION 2.8.9) 

set(CMAKE_POSITION_INDEPENDENT_CODE ON)
set(CMAKE_INSTALL_PREFIX "${PROJECT_SOURCE_DIR}")

add_definitions(-DLOAD_X11)

add_subdirectory(glsdk)
set(glsdk_INCLUDE_DIRS 
    "${glsdk_SOURCE_DIR}/freeglut/include"
    "${glsdk_SOURCE_DIR}/glfw/include"
    "${glsdk_SOURCE_DIR}/glload/include"
    "${glsdk_SOURCE_DIR}/glutil/include"
    "${glsdk_SOURCE_DIR}/glmesh/include"
    "${glsdk_SOURCE_DIR}/glimg/include"
    "${glsdk_SOURCE_DIR}/glm"
    )
include_directories(${glsdk_INCLUDE_DIRS} ${framework_SOURCE_DIR})
set(glsdk_LIBS freeglut glfw glload glutil glmesh glimg)
add_subdirectory(framework)

add_subdirectory(Tut\ 01\ Hello\ Triangle)
add_subdirectory(Tut\ 02\ Playing\ with\ Colors)
add_subdirectory(Tut\ 03\ OpenGLs\ Moving\ Triangle)
add_subdirectory(Tut\ 04\ Objects\ at\ Rest)
add_subdirectory(Tut\ 05\ Objects\ in\ Depth)
add_subdirectory(Tut\ 06\ Objects\ in\ Motion)
add_subdirectory(Tut\ 07\ World\ in\ Motion)
add_subdirectory(Tut\ 08\ Getting\ Oriented)
add_subdirectory(Tut\ 09\ Lights\ on)
add_subdirectory(Tut\ 10\ Plane\ Lights)
add_subdirectory(Tut\ 11\ Shinies)
add_subdirectory(Tut\ 12\ Dynamic\ Range)
add_subdirectory(Tut\ 13\ Impostors)
add_subdirectory(Tut\ 14\ Textures\ Are\ Not\ Pictures)
add_subdirectory(Tut\ 15\ Many\ Images)
add_subdirectory(Tut\ 16\ Gamma\ and\ Textures)
add_subdirectory(Tut\ 17\ Spotlight\ on\ Textures)

file(COPY data DESTINATION ${CMAKE_CURRENT_BINARY_DIR})