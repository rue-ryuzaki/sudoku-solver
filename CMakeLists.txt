project("sudoku-solver")
cmake_minimum_required(VERSION 3.2)

if (MSVC)
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} /W4 /EHsc")
else()
    set(CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -Wall -Wold-style-cast -Wextra -Wundef -Wsign-compare -Wconversion -Wpointer-arith -Weffc++ -Wnon-virtual-dtor")
endif()

if (NOT CMAKE_CXX_STANDARD)
    set(CMAKE_CXX_STANDARD 11)
endif()
set(CMAKE_CXX_STANDARD_REQUIRED ON)

include_directories(include)
include_directories(third_party)

file(GLOB_RECURSE PROJECT_HEADERS "include/*.h*")
file(GLOB_RECURSE PROJECT_SOURCES "src/*.c*")

set(SRC_LIST ${PROJECT_SOURCES} ${PROJECT_HEADERS})

add_executable(${PROJECT_NAME} ${SRC_LIST})
