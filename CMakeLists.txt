cmake_minimum_required(VERSION 3.10)

project(3D_Square)

# Find OpenGL
find_package(OpenGL REQUIRED)

# Add source files
add_executable(3D_Square src/main.cpp src/glad.c)

# Include directories
target_include_directories(3D_Square PRIVATE include)

# Link libraries
target_link_libraries(3D_Square PRIVATE OpenGL::GL)

# Add GLFW (if installed via package manager)
find_package(glfw3 REQUIRED)
target_link_libraries(3D_Square PRIVATE glfw)

# If using GLM
find_package(glm REQUIRED)
target_include_directories(3D_Square PRIVATE ${GLM_INCLUDE_DIRS})
