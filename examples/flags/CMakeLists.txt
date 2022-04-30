add_executable(flags WIN32 MACOSX_BUNDLE flags.c ${TIGR_ADDITIONAL_SOURCES})
target_link_libraries(flags PUBLIC ${TIGR_TARGET_LINK_LIBRARIES})
target_include_directories(flags PUBLIC ${TIGR_TARGET_INCLUDES})