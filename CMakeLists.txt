
cmake_minimum_required(VERSION 3.15)
project(univariate-piop LANGUAGES CXX)

# Add the MCL library
add_subdirectory(third_party/mcl)

# Your source files
file(GLOB SRC src/*.cpp)

# Build the executable
add_executable(piop-test ${SRC})

# Link MCL and set C++17
target_include_directories(piop-test PRIVATE ${CMAKE_CURRENT_SOURCE_DIR}/third_party/mcl/include)
target_link_libraries(piop-test PRIVATE mcl)
set_target_properties(piop-test PROPERTIES CXX_STANDARD 17 CXX_EXTENSIONS OFF)
