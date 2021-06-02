set(gnulib_SRCS
	basename-lgpl.c
	byteswap.h
	dirname.c
	dirname.h
	dirname.h
	dosname.h
	error.c
	error.h
	exitfail.c
	exitfail.h
	getprogname.c
	getprogname.h
	gettext.h
	minmax.h
	msvc-inval.c
	msvc-inval.h
	msvc-nothrow.c
	msvc-nothrow.h
	progname.c
	progname.h
	strndup.c
	version-etc.c
	version-etc.h
	xalloc-oversized.h
	xalloc.h
	xalloc-die.c
	xasprintf.c
	xmalloc.c
	xsize.c
	xsize.h
    xvasprintf.h
	xvasprintf.c
)

add_library(gnulib STATIC ${gnulib_SRCS})
target_include_directories(gnulib PRIVATE ./ ../)
