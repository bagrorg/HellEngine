# Add source to this project's executable.
add_executable(HellEngine
    main.cpp
    vk_engine.cpp
    vk_engine.h
    vk_types.h
    vk_initializers.cpp
    vk_initializers.h)

# if (WIN32)
#     set_property(TARGET HellEngine PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "$<TARGET_FILE_DIR:HellEngine>")
# endif ()

target_include_directories(HellEngine PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")
#target_link_libraries(HellEngine vkbootstrap vma glm tinyobjloader imgui stb_image Vulkan::Vulkan sdl2)
target_link_libraries(HellEngine Vulkan::Vulkan imgui SDL2-static) 

add_dependencies(HellEngine Shaders)
