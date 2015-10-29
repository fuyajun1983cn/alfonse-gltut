project(framework)

add_definitions(-Wno-deprecated)
add_definitions(-DLOAD_X11)

set(framework_SRC
    framework.cpp  
    Mesh.cpp  
    Scene.cpp  
    Timer.cpp
    )

add_library(framework SHARED ${framework_SRC})
target_link_libraries(framework ${glsdk_LIBS} GL GLU)
