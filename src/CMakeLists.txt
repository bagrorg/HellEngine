# Add source to this project's executable.
add_executable(HellEngine
    main.cpp
    vk_engine.cpp
    vk_engine.h
    vk_types.h
    vk_initializers.cpp
    vk_initializers.h)


set_property(TARGET HellEngine PROPERTY VS_DEBUGGER_WORKING_DIRECTORY "$<TARGET_FILE_DIR:HellEngine>")

target_include_directories(HellEngine PUBLIC "${CMAKE_CURRENT_SOURCE_DIR}")
target_link_libraries(HellEngine vkbootstrap vma glm tinyobjloader imgui stb_image)

target_link_libraries(HellEngine Vulkan::Vulkan sdl2)

add_dependencies(HellEngine Shaders)
