cmake_minimum_required(VERSION 3.1)
project(global_map_api)

find_package(catkin_simple REQUIRED)
catkin_simple(ALL_DEPS_REQUIRED)

add_definitions(--std=c++17 -Wno-unknown-pragmas -DVISUALIZATION)

cs_add_library(${PROJECT_NAME}_lib
    src/global_map_api.cc
)

cs_add_executable(${PROJECT_NAME}
    src/main.cc
)
target_link_libraries(${PROJECT_NAME} ${PROJECT_NAME}_lib)

cs_install()
cs_export()
