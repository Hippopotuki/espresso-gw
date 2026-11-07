cmake_minimum_required(VERSION 3.20)

project(vpn_gateway
	VERSION 0.1.0
	LANGUAGES CXX
)

add_executable(vpn_gateway
	main.cpp
)

target_compile_options(vpn_gateway PRIVATE 
	-Wall
    	-Wextra
    	-Wpedantic
    	-Wshadow
    	-Wconversion
    	-Wsign-conversion
)

target_compile_features(vpn_gateway PRIVATE cxx_std_20)