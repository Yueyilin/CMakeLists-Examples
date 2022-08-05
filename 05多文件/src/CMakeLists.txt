project(exe)
set(CMAKE_RUNTIME_OUTPUT_DIRECTORY ${CMAKE_SOURCE_DIR}/bin)
# Create the executable
add_executable(${PROJECT_NAME} 
    main.cpp
)

# Link the static library from subproject1 using its alias lib::Hello
# This will cause the include directories for that target to be added to this project
target_link_libraries(${PROJECT_NAME}
    lib::Hello
)