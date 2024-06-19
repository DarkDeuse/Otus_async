cmake_minimum_required(VERSION 3.20)

if (DEFINED ENV{TRAVIS_BUILD_NUMBER})
	project( async VERSION 0.0.$ENV{TRAVIS_BUILD_NUMBER})
else()
	project( async VERSION 99.99.999)
endif()

add_subdirectory (${PROJECT_SOURCE_DIR}/libs)
add_subdirectory (${PROJECT_SOURCE_DIR}/src)
