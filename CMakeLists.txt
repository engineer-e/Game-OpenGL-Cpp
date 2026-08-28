cmake_minimum_required(VERSION 3.25)

project(
    ComputerGraphics
    VERSION 1.0.0
    LANGUAGES CXX
)

# ------------------------------------------------------------
# C++ Standard
# ------------------------------------------------------------

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_CXX_EXTENSIONS OFF)

# ------------------------------------------------------------
# Find dependencies
# ------------------------------------------------------------

find_package(OpenGL REQUIRED)
find_package(GLEW CONFIG REQUIRED)
find_package(glfw3 CONFIG REQUIRED)
find_package(glm CONFIG REQUIRED)
find_package(assimp CONFIG REQUIRED)
find_package(FreeGLUT CONFIG REQUIRED)





add_subdirectory(src)
add_subdirectory(app)

set(COMPUTER_GRAPHICS_OUTPUT_DIR
    "${CMAKE_SOURCE_DIR}/output/ComputerGraphics"
)

set_target_properties(
    ComputerGraphics
    PROPERTIES

        RUNTIME_OUTPUT_DIRECTORY
            "${COMPUTER_GRAPHICS_OUTPUT_DIR}"

        RUNTIME_OUTPUT_DIRECTORY_DEBUG
            "${COMPUTER_GRAPHICS_OUTPUT_DIR}/Debug"

        RUNTIME_OUTPUT_DIRECTORY_RELEASE
            "${COMPUTER_GRAPHICS_OUTPUT_DIR}/Release"
)