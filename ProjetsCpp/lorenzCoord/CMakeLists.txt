#you can change the minimum version of cmake below
cmake_minimum_required(VERSION 3.5.1)

project (mecsycoWrapper )

set(PROJECT_VERSION "1.0.0")

set(CMAKE_CXX_STANDARD 11)

set (CMAKE_CXX_FLAGS "${CMAKE_CXX_FLAGS} -std=c++1y -pedantic -Wall -Wextra -Wcast-align -Wcast-qual -Wctor-dtor-privacy -Wdisabled-optimization -Wformat=2 -Winit-self -Wlogical-op -Wmissing-declarations -Wmissing-include-dirs -Wnoexcept    -Woverloaded-virtual -Wredundant-decls -Wsign-conversion -Wstrict-null-sentinel -Wstrict-overflow=5 -Wswitch-default -Wundef -Werror -Wno-unused")

file(GLOB SOURCES "src/*.cpp")

# for boost
find_package(Boost)
IF (Boost_FOUND)
include_directories(${Boost_INCLUDE_DIR})
endif()

set (Boost_USE_STATIC_LIBS OFF) # linking boost dynamically

find_package (Boost COMPONENTS REQUIRED system thread)


#you can change the target name, by you have to set the same name in add_library(...) and
#target_link_libraries(...) 
add_library(lorenzYcpp SHARED ${SOURCES})

target_link_libraries (lorenzYcpp ${Boost_LIBRARIES})
