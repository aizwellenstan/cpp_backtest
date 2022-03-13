add_library (Modules
  Backtest.h
  Backtest.cpp)

install (TARGETS Modules DESTINATION bin)
install (FILES Backtest.h DESTINATION include)
