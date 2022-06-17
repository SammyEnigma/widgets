
cmake_minimum_required( VERSION 2.8.11 )

project( widgets )

# Find includes in corresponding build directories
set( CMAKE_INCLUDE_CURRENT_DIR ON )
# Instruct CMake to run moc automatically when needed.
set( CMAKE_AUTOMOC ON )

option( BUILD_EXAMPLES "Build examples" ON )

if( ${CMAKE_CXX_COMPILER_ID} STREQUAL "GNU" )
  set( CMAKE_CXX_FLAGS ${CMAKE_CXX_FLAGS} "-fPIC" )
endif()

find_package( Qt6Core REQUIRED )
find_package( Qt6Gui REQUIRED )
find_package( Qt6Widgets REQUIRED )

set( CMAKE_ARCHIVE_OUTPUT_DIRECTORY ${PROJECT_BINARY_DIR}/lib )

add_subdirectory( src )

if( BUILD_EXAMPLES )
	add_subdirectory( examples )
endif()
