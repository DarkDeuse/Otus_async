cmake_minimum_required(VERSION 3.20)

if (DEFINED ENV{REALISE_BUILD_NUMBER})
	project(async VERSION 0.0.$ENV{REALISE_BUILD_NUMBER})
else()
	project(async VERSION 99.99.999)
endif()

configure_file(version.h.in version.h)

add_subdirectory (${PROJECT_SOURCE_DIR}/libs)
add_subdirectory (${PROJECT_SOURCE_DIR}/src)
