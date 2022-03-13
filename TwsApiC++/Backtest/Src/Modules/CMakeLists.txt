add_library (BacktestModules
  Backtest.h
  Backtest.cpp)

install (TARGETS BacktestModules DESTINATION bin)
install (FILES Backtest.h DESTINATION include)
