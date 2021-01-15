cmake_minimum_required(VERSION 3.10.2)

project(FSH LANGUAGES CXX)

cmake_policy(SET CMP0048 NEW)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_FLAGS "-Wall -Wextra -Wpedantic") # Last option is because of a problem with GCC9. Try to remove with more releases of the compiler

set(default_build_type "Release")

find_package(OpenMP COMPONENTS CXX)

add_executable(fsh src/FSH.cpp src/Chrono/Chrono.cpp src/Input/Input.cpp src/Input/Sequence.cpp src/Input/FileScan.cpp src/Utilities/Utilities.cpp src/Parameter/Parameter.cpp src/FSH/FSH.cpp src/Spaced/SpacedQmer.cpp)
target_link_libraries(fsh OpenMP::OpenMP_CXX)
