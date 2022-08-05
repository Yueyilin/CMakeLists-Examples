# Set the project name
project (sublibrary1)

# Add a library with the above sources
add_library(${PROJECT_NAME}
    Hello.cpp
)
add_library(lib::Hello ALIAS ${PROJECT_NAME})

target_include_directories( ${PROJECT_NAME}
    PUBLIC
        ${PROJECT_SOURCE_DIR}
)
