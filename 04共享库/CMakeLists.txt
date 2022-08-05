cmake_minimum_required(VERSION 3.5)

project(hello_library)


# set out dir
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)
set(EXE_SOURCES
    src/main.cpp
)
set(SHARED_LIB_SOURCES
    src/Hello.cpp
)
# file(GLOB SOURCES "src/*.cpp")

############################################################
# Create a library
############################################################

#Generate the static library from the library sources
add_library(hello_lib SHARED
    ${SHARED_LIB_SOURCES}
)
add_library(lib::hello ALIAS hello_lib)

target_include_directories(hello_lib
    PUBLIC
        ${PROJECT_SOURCE_DIR}/include
)


############################################################
# Create an executable
############################################################

# Add an executable with the above sources
add_executable(exe
    ${EXE_SOURCES}
)

# link the new hello_library target with the hello_binary target
target_link_libraries(exe
    PRIVATE
        lib::hello
)
