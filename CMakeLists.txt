cmake_minimum_required(VERSION 3.14)
project(PlatformerSFML)

set(CMAKE_CXX_STANDARD 14)

if(WIN32)
    set(SFML_STATIC_LIBRARIES TRUE)
    set(CMAKE_EXE_LINKER_FLAGS "-static")
endif()


find_package(SFML 2.5.1 COMPONENTS system window graphics network audio)
set(SOURCE_FILES src/main.cpp src/Game.cpp src/Game.h src/Creature.cpp src/Creature.h src/Solids.cpp src/Solids.h src/Player.cpp src/Player.h src/Enemy.cpp src/Enemy.h src/Platform.cpp src/Platform.h src/Item.cpp src/Item.h src/Icon.cpp src/Icon.h src/Objective.cpp src/Objective.h src/Spirit.cpp src/Spirit.h src/Door.cpp src/Door.h src/Bar.cpp src/Bar.h)
add_executable(PlatformerSFML ${SOURCE_FILES})

set(CMAKE_MODULE_PATH "${CMAKE_CURRENT_LIST_DIR}/cmake_modules")

target_link_libraries (PlatformerSFML sfml-graphics sfml-window sfml-system sfml-network sfml-audio)
file(COPY ${CMAKE_CURRENT_SOURCE_DIR}/Data/ DESTINATION ${CMAKE_CURRENT_BINARY_DIR}/Data/)