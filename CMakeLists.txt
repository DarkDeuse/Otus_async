cmake_minimum_required(VERSION 3.2) 

set(PATCH_VERSION "1" CACHE INTERNAL "Patch version")
set(PROJECT_VESRION 0.0.${PATCH_VERSION})

project(async VERSION ${PROJECT_VESRION})


add_executable(async main.cpp)
set_target_properties(async PROPERTIES CXX_STANDARD 17 CXX_STANDARD_REQIRED ON)
target_link_libraries(async PRIVATE
printer filePrinter consolePrinter libinterpret libasync )

add_subdirectory (${PROJECT_SOURCE_DIR}/libs)

if(MSVC)
	target_compile_options(async PRIVATE /W4)
else()
	target_compile_options(async PRIVATE -Wall -Wextra -Werror)
endif()

install(TARGETS async DESTINATION bin)
set(CPACK_GENERATOR DEB)
set(CPACK_PACKAGE_VERSION_MAJOR "${PROJECT_VERSION_MAJOR}")
set(CPACK_PACKAGE_VERSION_MINOR "${PROJECT_VERSION_MINOR}")
set(CPACK_PACKAGE_VERSION_PATCH "${PROJECT_VERSION_PATCH}")
set(CPACK_PACKAGE_CONTACT example@example.com)
include(CPack)