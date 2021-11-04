
project( widgets )

find_package( Qt6Core REQUIRED )
find_package( Qt6Widgets REQUIRED )

set( SRC meter.hpp
	meter.cpp )
    
include_directories( ${CMAKE_CURRENT_SOURCE_DIR} )

include_directories( ${Qt5Core_INCLUDE_DIRS}
	${Qt5Gui_INCLUDE_DIRS}
	${Qt5Widgets_INCLUDE_DIRS} )

add_library( widgets STATIC ${SRC} )

target_link_libraries( widgets Qt6::Widgets Qt6::Core )

set_property( TARGET widgets PROPERTY CXX_STANDARD 14 )

