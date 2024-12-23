cmake_minimum_required(VERSION 3.10)

project(auto_stream_plugin)

# OBS SDK-ni aniqlash
set(OBS_INCLUDE_DIR "/path/to/obs-studio/libobs")
set(OBS_FRONTEND_LIB "/path/to/obs-studio/UI/frontend-api")

# Kompilyator flaglari
set(CMAKE_CXX_STANDARD 17)

# OBS header va kutubxonalarini ulash
include_directories(${OBS_INCLUDE_DIR})
link_directories(${OBS_FRONTEND_LIB})

# Plaginning asosiy kodi
add_library(${PROJECT_NAME} MODULE auto_stream_plugin.cpp)
target_link_libraries(${PROJECT_NAME} obs frontend-api)
