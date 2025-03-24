cmake_minimum_required(VERSION 3.13)

project(scpi-parser LANGUAGES C)

# Füge alle C-Dateien aus dem src-Verzeichnis hinzu
file(GLOB SCPI_SOURCES ${CMAKE_CURRENT_SOURCE_DIR}/src/*.c)

# Erstelle eine statische Bibliothek
add_library(scpi-parser STATIC ${SCPI_SOURCES})

# Füge das Include-Verzeichnis hinzu
target_include_directories(scpi-parser PUBLIC ${CMAKE_CURRENT_SOURCE_DIR}/inc)

# Debug-Symbole aktivieren
target_compile_options(scpi-parser PRIVATE -g)
