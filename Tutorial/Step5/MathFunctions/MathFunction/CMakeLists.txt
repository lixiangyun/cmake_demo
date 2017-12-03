# first we add the executable that generates the table
# add the binary tree directory to the search path for include files
include_directories( ${CMAKE_SOURCE_DIR}/include )

# add the command to generate the source code
add_custom_command (
  OUTPUT ${CMAKE_SOURCE_DIR}/include/Table.h
  COMMAND MakeTable ${CMAKE_SOURCE_DIR}/include/Table.h
  DEPENDS MakeTable
  )

# add the main library
add_library(MathFunctions SHARED mysqrt.def mysqrt.cxx ${CMAKE_SOURCE_DIR}/include/Table.h  )

install (TARGETS MathFunctions DESTINATION bin)
install (FILES MathFunctions.h DESTINATION include)
