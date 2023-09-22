cmake_minimum_required(VERSION 3.12)
project(ACatGame)

set(CMAKE_CXX_STANDARD 11)

set(SDL2_DIR "C:/SDL2-2.28.1")

list(APPEND CMAKE_PREFIX_PATH "${SDL2_DIR}/cmake")
list(APPEND CMAKE_PREFIX_PATH "${SDL2_DIR}/lib/x64")

find_package(SDL2 REQUIRED)

if(SDL2_FOUND)
    set(SOURCES
        src/main.cpp
    )

    add_executable(${PROJECT_NAME} ${SOURCES})

    target_link_libraries(${PROJECT_NAME} SDL2::SDL2)

else()
    message(FATAL_ERROR "SDL2 not found. Please install SDL2 or specify its location using SDL2_DIR.")
endif()
