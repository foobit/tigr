add_executable(shader WIN32 MACOSX_BUNDLE shader.c ${TIGR_ADDITIONAL_SOURCES})
target_link_libraries(shader PUBLIC ${TIGR_TARGET_LINK_LIBRARIES})
target_include_directories(shader PUBLIC ${TIGR_TARGET_INCLUDES})