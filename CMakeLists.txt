cmake_minimum_required(VERSION 3.12)
project(cpp_app)

set(CMAKE_RUNTIME_OUTPUT_DIRECTORY "../exe")

include_directories(./include)
link_directories(./lib)

file(GLOB sourcefiles "*.h" "*.cpp" "lib/imgui/*.h" "lib/imgui/*.cpp" "lib/imgui/backends/*.h" "lib/imgui/backends/*.cpp")
add_executable(${PROJECT_NAME} ${sourcefiles}
    src/sub_module.h src/sub_module.cpp
)

find_package(OpenGL)
target_link_libraries(${PROJECT_NAME} ${OPENGL_LIBRARIES} SDL2_image libSDL2_ttf SDL2 SDL2main)