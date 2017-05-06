cmake_minimum_required(VERSION 2.8.12)
project(DerelictSDL2 D)
list(APPEND CMAKE_MODULE_PATH
    "${CMAKE_CURRENT_SOURCE_DIR}/cmake")

find_package(Derelict REQUIRED
    COMPONENTS
        util)

include_directories("${CMAKE_CURRENT_SOURCE_DIR}/source")
add_library(DerelictSDL2 STATIC
    source/derelict/sdl2/functions.d
    source/derelict/sdl2/image.d
    source/derelict/sdl2/mixer.d
    source/derelict/sdl2/net.d
    source/derelict/sdl2/sdl.d
    source/derelict/sdl2/ttf.d
    source/derelict/sdl2/types.d)
target_link_libraries(DerelictSDL2
    Derelict::util)

install(
    TARGETS             DerelictSDL2
    ARCHIVE DESTINATION lib
    LIBRARY DESTINATION lib
    RUNTIME DESTINATION bin)
install(
    DIRECTORY   source/
    DESTINATION include/d)
