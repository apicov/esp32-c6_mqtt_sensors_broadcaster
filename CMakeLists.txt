# The following lines of boilerplate have to be in your project's
# CMakeLists in this exact order for cmake to work correctly
cmake_minimum_required(VERSION 3.16)

set(CMAKE_CXX_STANDARD 17)

# Suppress warnings about format specifiers
add_compile_options(-Wno-format)

# Add esp_mcp_bridge component path
set(EXTRA_COMPONENT_DIRS ./firmware/components)

include($ENV{IDF_PATH}/tools/cmake/project.cmake)
# "Trim" the build. Include the minimal set of components, main, and anything it depends on.
idf_build_set_property(MINIMAL_BUILD ON)
project(esp32-c6-mcp-sensor-hub)
