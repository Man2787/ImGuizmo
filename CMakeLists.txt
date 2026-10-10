cmake_minimum_required(VERSION 3.16)
project(ImGuizmo LANGUAGES CXX)

set(CMAKE_CXX_STANDARD 17)
set(CMAKE_CXX_STANDARD_REQUIRED ON)

add_library(imguizmo STATIC
    src/ImGuizmo.cpp
    src/GraphEditor.cpp
    src/ImCurveEdit.cpp
    src/ImGradient.cpp
    src/ImSequencer.cpp
    src/ImVectorEditor.cpp
)

add_library(imguizmo::imguizmo ALIAS imguizmo)

target_link_libraries(imguizmo PUBLIC
    imgui # is avalible in another spot
)

target_include_directories(imguizmo PUBLIC
    $<BUILD_INTERFACE:${CMAKE_CURRENT_SOURCE_DIR}/src>
    $<INSTALL_INTERFACE:include>
)
