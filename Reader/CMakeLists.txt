cmake_minimum_required (VERSION 3.0)
project (PPDBReader)

include_directories (${INC})

add_library (PPDBReader
    CoreReader.cpp
    Streams.cpp
    Tables.cpp ${INC}/PPDBReader.hpp)

set_target_properties(PPDBReader PROPERTIES PUBLIC_HEADER "${INC}/PPDBReader.hpp;${INC}/platform.hpp")

install(TARGETS PPDBReader DESTINATION lib/$<CONFIG>/${CMAKE_GENERATOR_PLATFORM} PUBLIC_HEADER DESTINATION include/PPDB)