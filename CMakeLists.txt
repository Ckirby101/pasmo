cmake_minimum_required(VERSION 3.12)
project(pasmo)

set(CMAKE_CXX_STANDARD 14)

include_directories(pasmo)

add_executable(pasmo
        pasmo/asm.cpp
        pasmo/asm.h
        pasmo/asmfile.cpp
        pasmo/asmfile.h
        pasmo/cpc.cpp
        pasmo/cpc.h
        pasmo/pasmo.cpp
        pasmo/pasmotypes.cpp
        pasmo/pasmotypes.h
        pasmo/spectrum.cpp
        pasmo/spectrum.h
        pasmo/tap.cpp
        pasmo/tap.h
        pasmo/token.cpp
        pasmo/token.h
        pasmo/trace.cpp
        pasmo/trace.h
        pasmo/tzx.cpp
        pasmo/tzx.h)
