cmake_minimum_required(VERSION 3.0.0)
project(tigr LANGUAGES C)

# default building amalgamated as off as the repo has it pre built
option(TIGR_BUILD_AMALGAMATED "Build the amalgamated source" OFF)
option(TIGR_BUILD_EXAMPLES "Build the examples" ON)

# set tigr defines
if(WIN32)
    list(APPEND TIGR_TARGET_LINK_LIBRARIES
        "opengl32"
        "gdi32")
elseif(APPLE)
    list(APPEND TIGR_TARGET_LINK_LIBRARIES 
        "-framework OpenGL"
        "-framework Cocoa")
elseif(UNIX)
    list(APPEND TIGR_TARGET_LINK_LIBRARIES
        "GLU"
        "GL"
        "X11")
endif()

list(APPEND TIGR_TARGET_INCLUDES
    "${PROJECT_SOURCE_DIR}")

list(APPEND TIGR_ADDITIONAL_SOURCES
    "${PROJECT_SOURCE_DIR}/tigr.c")
    
# helper function to copy loose assets to the output folder
function(target_copy_asset target file)
    add_custom_command(
        TARGET ${target} POST_BUILD
        COMMAND ${CMAKE_COMMAND} -E copy "${CMAKE_CURRENT_SOURCE_DIR}/${file}" "${CMAKE_CURRENT_BINARY_DIR}/${file}"
        DEPENDS "${CMAKE_CURRENT_SOURCE_DIR}/${file}")
endfunction()

# add sources
if(TIGR_BUILD_AMALGAMATED)
    add_subdirectory(src)
endif()

if(TIGR_BUILD_EXAMPLES)
    add_subdirectory(examples)
endif()
