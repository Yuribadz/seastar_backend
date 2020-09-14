cmake_minimum_required(VERSION 3.2 FATAL_ERROR)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
project(seastar_backend)

find_package(Seastar CONFIG REQUIRED)
# Target server
add_executable(server src/server.cpp)
target_include_directories(server
        PUBLIC
        PRIVATE
        )
target_compile_definitions(server
        PRIVATE
        )
target_sources(server
        PRIVATE
        src/server.cpp
        )
target_compile_options(server
        PUBLIC
        )
target_compile_features(server
        PUBLIC
        )
target_link_libraries(server
        PUBLIC
        Seastar::seastar
        )
set_target_properties(server
        PROPERTIES
        ARCHIVE_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
        LIBRARY_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/lib"
        RUNTIME_OUTPUT_DIRECTORY "${CMAKE_BINARY_DIR}/bin"
        )