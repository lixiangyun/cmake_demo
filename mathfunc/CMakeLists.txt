add_library(mathfunc mathfunc.c)
TARGET_LINK_LIBRARIES(mathfunc m)

install (TARGETS mathfunc DESTINATION bin)
install (FILES mathfunc.h DESTINATION include)
