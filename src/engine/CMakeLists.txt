cmake_minimum_required(VERSION 3.21)

project(miniex LANGUAGES CXX)

add_executable(miniex ./main.cpp)

target_compile_features(miniex PRIVATE cxx_std_17)

if(MSVC)
	target_compile_options(miniex PRIVATE /W4)
else()
	target_compile_options(miniex PRIVATE -Wall -Wextra -Wpedantic)
endif()

option(ENABBLE_SANITIZERS "Enable ADdressSanitizer and UBSan" OFF)

if(ENABLE_SANITIZERS)
	if(WIN32 OR NOT CMAKE_CXX_COMPILER_ID MATCHES "Clang|GNU")
		message(FATAL_ERROR "This sanitizer configuration is not for GCC/Clang on Linux")
	endif()

	target_compile_options(miniex PRIVATE -fsanitize=address,undefined -fno-omit-frame-pointer)

	target_link_options(miniex PRIVATE -fsanitize=address,undefined)
endif()

if(BUILD_TESTING)
	add_test(NAME smoke COMMAND miniex)

	set_tests_properties(smoke PROPERTIES PASS_REGULAR_EXPRESSIN "Smoke Tests enabled.")
endif()
