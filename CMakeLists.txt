cmake_minimum_required(VERSION 3.5.0)
project(star-shoot VERSION 0.1.0 LANGUAGES C CXX)

include(CTest)
enable_testing()

file(GLOB SOURCES
    src/*.cpp
)
file(GLOB HEADERS
    hrd/*.hpp
)

add_executable(star-shoot ${SOURCES})

add_subdirectory(SDL)
target_link_libraries(star-shoot PRIVATE SDL3::SDL3)

set(CPACK_PROJECT_NAME ${PROJECT_NAME})
set(CPACK_PROJECT_VERSION ${PROJECT_VERSION})
include(CPack)
