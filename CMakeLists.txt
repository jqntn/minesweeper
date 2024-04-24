cmake_minimum_required(VERSION 3.19)

project(minesweeper)

add_executable(minesweeper "minesweeper.c")

set_property(TARGET minesweeper PROPERTY C_STANDARD 99)
set_property(TARGET minesweeper PROPERTY C_STANDARD_REQUIRED ON)
set_property(TARGET minesweeper PROPERTY C_EXTENSIONS OFF)

include(FetchContent)
set(FETCHCONTENT_QUIET OFF)
FetchContent_Declare(
  raylib
  GIT_REPOSITORY https://github.com/raysan5/raylib.git
  GIT_TAG "5.0"
  GIT_PROGRESS TRUE
)
FetchContent_MakeAvailable(raylib)

target_link_libraries(minesweeper PRIVATE raylib)

target_compile_options(minesweeper PRIVATE "-Wall")