project(FLATBUFFEREXAMPLE)
cmake_minimum_required(VERSION 2.8.10)

set(FlatbufferRoot /Users/chenxiaotao03/Repositories/flatbuffers)

include_directories(${FlatbufferRoot}/include)
link_directories(${FlatbufferRoot}/build)

add_definitions(-Wall -Wextra -Wno-unused-function)
add_definitions(-std=c++11 -fPIC)

# sampleBinary
file(GLOB sampleBinary_SRC "sample_binary.cpp")
add_executable(sampleBinary ${sampleBinary_SRC})

# sample text
file(GLOB sampleText_SRC "sample_text.cpp")
add_executable(sampleText ${sampleText_SRC})
target_link_libraries(sampleText -lflatbuffers)
# sample parser
file(GLOB sampleParser_SRC "sample_parser.cpp")
add_executable(sampleParser ${sampleParser_SRC})

