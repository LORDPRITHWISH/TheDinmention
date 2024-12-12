cmake_minimum_required(VERSION 3.10)

project(openGL_testing)

# Find OpenGL
find_package(OpenGL REQUIRED)

# Add source files
add_executable(opcode src/main.cpp src/glad.c)

# Include directories
target_include_directories(opcode PRIVATE include)

# Link libraries
target_link_libraries(opcode PRIVATE OpenGL::GL)

# Add GLFW (if installed via package manager)
find_package(glfw3 REQUIRED)
target_link_libraries(opcode PRIVATE glfw)

# If using GLM
find_package(glm REQUIRED)
target_include_directories(opcode PRIVATE ${GLM_INCLUDE_DIRS})
