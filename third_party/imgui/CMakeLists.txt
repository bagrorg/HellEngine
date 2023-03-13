add_library(imgui STATIC)
target_include_directories(imgui PUBLIC imgui_src)
target_sources(imgui PRIVATE 
    imgui_src/imgui.h
    imgui_src/imgui.cpp

    imgui_src/imgui_demo.cpp
    imgui_src/imgui_draw.cpp
    imgui_src/imgui_widgets.cpp

    imgui_src/backends/imgui_impl_vulkan.cpp
    imgui_src/backends/imgui_impl_sdl2.cpp
)

target_link_libraries(imgui PUBLIC Vulkan::Vulkan SDL2-static)