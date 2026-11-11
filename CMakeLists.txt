cmake_minimum_required(VERSION 3.20)

project(espresso
	VERSION 0.1.0
	LANGUAGES CXX
)

add_library(espresso_core STATIC
    src/info.cpp
)

target_include_directories(espresso_core PUBLIC
    ${CMAKE_CURRENT_SOURCE_DIR}/src
)

add_executable(espresso
	src/main.cpp
)

target_compile_options(espresso_core PRIVATE 
	-Wall
    	-Wextra
    	-Wpedantic
    	-Wshadow
    	-Wconversion
    	-Wsign-conversion
)

target_compile_options(espresso PRIVATE 
	-Wall
    	-Wextra
    	-Wpedantic
    	-Wshadow
    	-Wconversion
    	-Wsign-conversion
)

target_link_libraries(espresso PRIVATE espresso_core)
target_compile_features(espresso_core PUBLIC cxx_std_20)