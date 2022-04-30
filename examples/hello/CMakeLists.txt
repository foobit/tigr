add_executable(hello WIN32 MACOSX_BUNDLE hello.c ${TIGR_ADDITIONAL_SOURCES})
target_link_libraries(hello PUBLIC ${TIGR_TARGET_LINK_LIBRARIES})
target_include_directories(hello PUBLIC ${TIGR_TARGET_INCLUDES})