cmake_minimum_required (VERSION 3.15)

project(conan_ex)

# include(/home/jeff/dev/sfml-ex/build/conanbuildinfo.cmake)
include(${CMAKE_BINARY_DIR}/conanbuildinfo.cmake)
conan_basic_setup()

SET(CMAKE_CXX_FLAGS "-Wall -Wextra -std=c++11")

add_executable(
    ${PROJECT_NAME}
    src/main.cpp
    )

target_link_libraries(
    ${PROJECT_NAME}
    ${CONAN_LIBS}
    )
