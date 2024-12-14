cmake_minimum_required(VERSION 3.31 FATAL_ERROR)

project(CudaTemplate CUDA)

set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Download and include CCCL Libraries
include(cmake/CPM.cmake)
set(CCCL_REPOSITORY "nvidia/cccl" CACHE STRING "GitHub repository to fetch CCCL from")
set(CCCL_TAG "main" CACHE STRING "Git tag/branch to fetch from CCCL repository")
CPMAddPackage(
    NAME CCCL
    GITHUB_REPOSITORY ${CCCL_REPOSITORY}
    GIT_TAG ${CCCL_TAG}
)

set(CMAKE_CUDA_ARCHITECTURES native)

add_executable(CudaTemplate src/main.cu)

target_link_libraries(CudaTemplate PRIVATE CCCL::CCCL)