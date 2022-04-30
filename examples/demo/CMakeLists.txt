# change default CXX support
project(demo LANGUAGES CXX C)

add_executable(demo WIN32 MACOSX_BUNDLE demo.cpp ${TIGR_ADDITIONAL_SOURCES})
target_link_libraries(demo PUBLIC ${TIGR_TARGET_LINK_LIBRARIES})
target_include_directories(demo PUBLIC ${TIGR_TARGET_INCLUDES})
target_copy_asset(demo "greeting.txt")
target_copy_asset(demo "squinkle.png")
