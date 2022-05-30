project(LongScroll LANGUAGES CXX)
cmake_minimum_required(VERSION 3.2)
set(CMAKE_CXX_STANDARD 17)

set(CMAKE_AUTOMOC ON)
set(CMAKE_AUTOUIC ON)

aux_source_directory("${CMAKE_CURRENT_SOURCE_DIR}/src/" LONGSRCS)
include_directories("${CMAKE_CURRENT_SOURCE_DIR}/src/")
add_library(LongScroll STATIC ${LONGSRCS})

find_package(
    Qt5
    COMPONENTS Widgets
    REQUIRED)

target_include_directories(LongScroll PRIVATE Qt5::Widgets)
target_link_libraries(LongScroll PRIVATE Qt5::Widgets)
