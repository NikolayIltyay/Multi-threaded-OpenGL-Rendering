cmake_minimum_required(VERSION 3.16)
project(multithreaded_rendering)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)


set(SRC_DIR ${CMAKE_SOURCE_DIR}/src)

file(GLOB SRC_FILES ${SRC_DIR}/*.cpp)

add_executable(multithreaded_rendering ${SRC_FILES}
	${CMAKE_SOURCE_DIR}/glad/src/glad.c)

target_include_directories(multithreaded_rendering PRIVATE ${SRC_DIR} ${CMAKE_SOURCE_DIR}/third_party/glfw/include
	${CMAKE_SOURCE_DIR}/glad/include
)

find_package(OpenGL REQUIRED)

target_link_libraries(multithreaded_rendering PRIVATE
    ${CMAKE_SOURCE_DIR}/third_party/glfw/lib/glfw3.lib
    OpenGL::GL
)



