add_executable(clip WIN32 MACOSX_BUNDLE clip.c ${TIGR_ADDITIONAL_SOURCES})
target_link_libraries(clip PUBLIC ${TIGR_TARGET_LINK_LIBRARIES})
target_include_directories(clip PUBLIC ${TIGR_TARGET_INCLUDES})