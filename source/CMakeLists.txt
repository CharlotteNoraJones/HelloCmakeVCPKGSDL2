cmake_minimum_required(VERSION 3.28.1)

project(HelloSDL VERSION 1.0 LANGUAGES CXX)

find_package(SDL2 CONFIG REQUIRED)

add_executable(HelloSDL main.cpp)

target_link_libraries(HelloSDL
        PRIVATE
        $<TARGET_NAME_IF_EXISTS:SDL2::SDL2main>
        $<IF:$<TARGET_EXISTS:SDL2::SDL2>,SDL2::SDL2,SDL2::SDL2-static>
    )