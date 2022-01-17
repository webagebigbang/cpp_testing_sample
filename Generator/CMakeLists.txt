add_library(Generator STATIC Generator.cpp Generator.h)

target_include_directories(Generator INTERFACE ${CMAKE_CURRENT_SOURCE_DIR})

# this test is run separately
# enable_testing()

add_executable(GeneratorTest GeneratorTest.cpp)

target_link_libraries(GeneratorTest gtest_main Generator)

include(GoogleTest)
gtest_discover_tests(GeneratorTest)
