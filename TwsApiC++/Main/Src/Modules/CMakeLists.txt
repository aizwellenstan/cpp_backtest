add_library (Modules
  OrderExcute.h
  OrderExcute.cpp)

install (TARGETS Modules DESTINATION bin)
install (FILES OrderExcute.h DESTINATION include)
