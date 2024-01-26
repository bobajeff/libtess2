cmake_minimum_required(VERSION 3.0.0)
project(libtess2 VERSION 0.1.0 LANGUAGES C)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/Include")

file( GLOB ALL_SRCS "${CMAKE_CURRENT_SOURCE_DIR}/Source/*.c")


add_library(libtess2 STATIC ${ALL_SRCS})
target_include_directories(libtess2 PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}/Include")

# Stuff to build Example demo
# find_package(OpenGL REQUIRED)
# find_package(GLU REQUIRED)
# find_package(GLEW REQUIRED)

# include(FetchContent)

# FetchContent_Declare(
#         glfw
#         GIT_REPOSITORY https://github.com/glfw/glfw
# )
# FetchContent_MakeAvailable(glfw)
# add_library(nanosvg STATIC ${CMAKE_SOURCE_DIR}/Contrib/nanosvg.c)
# target_include_directories(nanosvg PUBLIC "${CMAKE_SOURCE_DIR}/Contrib")

# add_executable(example "${CMAKE_SOURCE_DIR}/Example/example.c")
# target_link_libraries(example PRIVATE ${OPENGL_LIBRARIES} ${GLU_LIBRARY} ${GLEW_LIBRARIES} libtess2 glfw nanosvg)
# target_include_directories(example PUBLIC ${OPENGL_INCLUDE_DIRS}  ${GLU_INCLUDE_DIRS}  ${GLEW_INCLUDE_DIRS} libtess2 glfw nanosvg)
# target_compile_definitions(example PUBLIC NANOVG_GLEW)
# ---------------------------------------------

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
