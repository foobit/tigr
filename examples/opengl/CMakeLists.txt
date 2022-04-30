add_executable(opengl WIN32 MACOSX_BUNDLE opengl.c ${TIGR_ADDITIONAL_SOURCES})
target_link_libraries(opengl PUBLIC ${TIGR_TARGET_LINK_LIBRARIES})
target_include_directories(opengl PUBLIC ${TIGR_TARGET_INCLUDES})