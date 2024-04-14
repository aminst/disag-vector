cmake_minimum_required(VERSION 3.29 FATAL_ERROR)
include(FetchContent)

add_subdirectory(faiss)

FetchContent_Declare(
    argparse
    GIT_REPOSITORY https://github.com/p-ranav/argparse.git
)
FetchContent_MakeAvailable(argparse)

FetchContent_Declare(
    json
    URL https://github.com/nlohmann/json/releases/download/v3.11.2/json.tar.xz)
FetchContent_MakeAvailable(json)

find_package(OpenMP REQUIRED)

add_executable(bench_hnsw bench_hnsw.cpp)
target_include_directories(bench_hnsw PUBLIC
    $<BUILD_INTERFACE:${PROJECT_SOURCE_DIR}>
)
target_link_libraries(bench_hnsw 
    faiss 
    OpenMP::OpenMP_CXX 
    argparse 
    nlohmann_json::nlohmann_json
)