# Set project
project(spdlog-tutorial)

# Set C++ standard
set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

# Set directories
set(CXX_CSRC_DIR ${CMAKE_CURRENT_SOURCE_DIR}/csrc)
set(CXX_INCLUDE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/include)

# Third-party libraries
set(THIRD_PARTY_DIR ${CMAKE_CURRENT_SOURCE_DIR}/3rdparty)   
add_subdirectory(${THIRD_PARTY_DIR}/spdlog)

# Add executable
add_executable(spdlog-tutorial ${CXX_CSRC_DIR}/main.cpp ${CXX_CSRC_DIR}/custom.cpp)

# Add include
target_include_directories(spdlog-tutorial PRIVATE ${CXX_INCLUDE_DIR} ${THIRD_PARTY_DIR}/spdlog/include)