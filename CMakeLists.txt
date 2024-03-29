project(cpp_experiments)
cmake_minimum_required(VERSION 3.22)

set(CMAKE_CXX_STANDARD 20)
set(CMAKE_CXX_STANDARD_REQUIRED ON)
set(CMAKE_EXPORT_COMPILE_COMMANDS ON)

include_directories("libs/")

add_library(ut "libs/ut.hpp")
set_target_properties(ut PROPERTIES LINKER_LANGUAGE CXX)

add_library(fraction "src/Fraction.cpp")
add_library(tekst "src/Tekst.cpp")
add_library(punkt "src/Punkt.cpp")
add_library(okrag "src/Okrag.cpp")
target_link_libraries(okrag punkt)

add_library(kolejka "src/Kolejka.cpp")

add_library(set "src/Set.cpp")

add_executable(tests "src/tests.cpp")
target_link_libraries(tests fraction tekst ut)

add_executable(kolejka_sample "src/kolejka_sample.cpp")
target_link_libraries(kolejka_sample kolejka)
