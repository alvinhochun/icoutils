set(common_SRCS
    common.h
    comparison.h
    error.c
    error.h
    hmap.c
    hmap.h
    io-utils.c
    io-utils.h
    intutil.c
    intutil.h
    llist.c
    llist.h
    strbuf.c
    strbuf.h
    string-utils.c
    string-utils.h
    tmap.c
    tmap.h
)

add_library(common STATIC ${common_SRCS})
target_include_directories(common PRIVATE ./ ../ ../lib)
target_link_libraries(common gnulib)
