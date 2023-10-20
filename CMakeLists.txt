cmake_minimum_required(VERSION 3.15)

set(CMAKE_OSX_DEPLOYMENT_TARGET "10.13" CACHE STRING "Minimum OS X deployment version")

project(cimgui)

set(CMAKE_CXX_STANDARD 11)
set(CMAKE_CXX_STANDARD_REQUIRED True)

include_directories(cimgui/imgui
    cimgui)

add_library(cimgui SHARED 
    cimgui/cimgui.cpp
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
    cimgui/imgui/imgui_tables.cpp)

target_compile_definitions(cimgui PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1)
set_target_properties(cimgui PROPERTIES PREFIX "")


add_library(cimguizmo SHARED 
    cimgui/cimgui.cpp
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
    cimgui/imgui/imgui_tables.cpp
	cimguizmo/cimguizmo.cpp
    cimguizmo/ImGuizmo/ImGuizmo.cpp)

target_compile_definitions(cimguizmo PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1)
set_target_properties(cimguizmo PROPERTIES PREFIX "")


add_library(cimplot SHARED 
    cimgui/cimgui.cpp
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
    cimgui/imgui/imgui_tables.cpp
	cimplot/cimplot.cpp
    cimplot/implot/implot.cpp
    cimplot/implot/implot_demo.cpp
    cimplot/implot/implot_items.cpp)

target_compile_definitions(cimplot PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1)
set_target_properties(cimplot PROPERTIES PREFIX "")


add_library(cimnodes SHARED 
    cimgui/cimgui.cpp
    cimgui/imgui/imgui.cpp
    cimgui/imgui/imgui_draw.cpp
    cimgui/imgui/imgui_demo.cpp
    cimgui/imgui/imgui_widgets.cpp
    cimgui/imgui/imgui_tables.cpp
	cimnodes/cimnodes.cpp
    cimnodes/imnodes/imnodes.cpp)

target_compile_definitions(cimnodes PUBLIC IMGUI_DISABLE_OBSOLETE_FUNCTIONS=1 IMNODES_NAMESPACE=imnodes)
set_target_properties(cimnodes PROPERTIES PREFIX "")