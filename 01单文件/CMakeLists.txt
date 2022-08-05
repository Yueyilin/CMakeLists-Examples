# cmake --version
cmake_minimum_required(VERSION 3.5)

# Set the ${PROJECT_NAME}
project (hello_cmake)

# set out dir
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

# Create a sources variable with a link to all cpp files to compile
set(SOURCES
    src/main.cpp
)

# Add an executable
add_executable(hello_cmake ${SOURCES})

