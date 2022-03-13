project(TWSAPICPP_TEST VERSION 1.0.0)

set(SOURCE_DIR ${CMAKE_CURRENT_SOURCE_DIR}/Src)

add_definitions(-D_REENTRANT -D_DEBUG)

set(THREADS_PREFER_PTHREAD_FLAG ON)
find_package(Threads REQUIRED)

include_directories(${API_INCLUDE_DIR} ${IB_POSIX_CLIENT_INCLUDE_DIR})

add_subdirectory (${SOURCE_DIR}/Modules)
include_directories(${SOURCE_DIR}/Modules)
add_executable (Backtest ${SOURCE_DIR}/Modules ${SOURCE_DIR}/Main.cpp)
target_link_libraries (Backtest BacktestModules)

# add_executable(Backtest ${SOURCE_DIR}/Main.cpp ${SOURCE_DIR}/Backtest.cpp ${SOURCE_DIR}/Backtest.h)

target_link_libraries(Backtest tws_cpp_api Threads::Threads)
target_compile_options(Backtest PRIVATE -Wall)