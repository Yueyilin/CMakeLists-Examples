# cmake --version
cmake_minimum_required(VERSION 3.5)

# Set the ${PROJECT_NAME}
project (hello_headers)

# set out dir
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)

# Create a sources variable with a link to all cpp files to compile
# set(SOURCES
#     src/Hello.cpp
#     src/main.cpp
# )
file(GLOB SOURCES "src/*.cpp")

# Add an executable
add_executable(exe ${SOURCES})

# Set the directories that should be included in the build command for this target
# when running g++ these will be included as -I/directory/path/
target_include_directories(exe
    PUBLIC
        ${PROJECT_SOURCE_DIR}/include
)

