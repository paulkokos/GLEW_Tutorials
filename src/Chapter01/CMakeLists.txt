add_executable(Chapter01 main.cpp ../../libs/main.cpp)

find_package(GLEW REQUIRED)
include_directories(${GLEW_INCLUDE_DIRS})
link_directories(${GLEW_LIBRARY_DIRS})
add_definitions(${GLEW_DEFINITIONS})

find_package(OpenGL REQUIRED)
if(NOT OPENGL_FOUND)
    message("ERROR: OpenGL not found")
endif(NOT OPENGL_FOUND)
set(GL_LIBRARY GL GLU X11)
set(CMAKE_CXX_STANDARD 20)
#set(CMAKE_PREFIX_PATH "/home/paulkokos/glew-2.1.0")
#set(CMAKE_LIBRARY_PATH "/home/paulkokos/glew-2.1.0/include/GL/")

#add_executable(GLEW_Tutorials main.cpp)
target_link_libraries(Chapter01 ${OPENGL_LIBRARIES} ${GLEW_LIBRARIES} glfw OpenGL::GL)