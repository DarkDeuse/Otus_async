cmake_minimum_required(VERSION 3.20)

set(PATCH_VERSION "1" CACHE INTERNAL "Patch version")
set(PROJECT_VESRION 0.0.${PATCH_VERSION})

configure_file(version.h.in version.h)

add_subdirectory (${PROJECT_SOURCE_DIR}/libs)
add_subdirectory (${PROJECT_SOURCE_DIR}/src)
