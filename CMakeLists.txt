project(icotool)

cmake_minimum_required(VERSION 3.7)


add_definitions(-DHAVE_CONFIG_H)
set(CMAKE_C_FLAGS "${CMAKE_C_FLAGS} -Werror=implicit-function-declaration -Werror")

add_subdirectory(lib)
add_subdirectory(common)


find_package(PNG REQUIRED)

set(CONFIG_H config.h)

set(ICOTOOL_SRCS
    icotool/create.c
    icotool/extract.c
    icotool/icotool.h
    icotool/main.c
    icotool/palette.c
    icotool/win32-endian.c
    icotool/win32-endian.h
    icotool/win32.h
    ${CONFIG_SRCS}
)

add_executable(icotool ${ICOTOOL_SRCS})
target_include_directories(icotool PRIVATE ./ lib/)
target_include_directories(icotool PRIVATE ${PNG_INCLUDE_DIRS})
target_link_libraries(icotool ${PNG_LIBRARY})
target_link_libraries(icotool gnulib common)

install(TARGETS icotool RUNTIME DESTINATION bin)
