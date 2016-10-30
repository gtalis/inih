#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([libinih], [r37], [https://github.com/benhoyt/inih])

AM_INIT_AUTOMAKE([dist-bzip2 no-dist-gzip foreign])

AC_CONFIG_SRCDIR([inih.h])
AC_CONFIG_HEADERS([config.h])

AC_CONFIG_FILES([Makefile])

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC
AM_PROG_CC_C_O
AC_PROG_LIBTOOL

# Checks for libraries.

# Library options
AC_ARG_ENABLE(
    multiline,
    AS_HELP_STRING([--disable-multiline],
    [disable multi-line value parsing, in the style of Python's configparser]),
    AC_DEFINE([INI_ALLOW_MULTILINE], [0], [multi-line value parsing not supported]),
    AC_DEFINE([INI_ALLOW_MULTILINE], [1], [allow multi-line value parsing])
)

AC_ARG_ENABLE(
    bom,
    AS_HELP_STRING([--disable-bom],
    [disable support of a UTF-8 BOM sequence (0xEF 0xBB 0xBF) at the start of the file]),
    AC_DEFINE([INI_ALLOW_BOM], [0], [BOM sequence not supported]),
    AC_DEFINE([INI_ALLOW_BOM], [1], [allow BOM sequence])
)

AC_ARG_ENABLE(
    inline-comments,
    AS_HELP_STRING([--disable-inline-comments],
    [disable inline comments support]),
    AC_DEFINE([INI_ALLOW_INLINE_COMMENTS], [0], [inline comments not supported]),
    AC_DEFINE([INI_ALLOW_INLINE_COMMENTS], [1], [allow inline comments])
)

AC_ARG_ENABLE(
    heap,
    AS_HELP_STRING([--enable-heap],
    [use heap (malloc/free) for memory allocation, otherwise use stack]),
    AC_DEFINE([INI_USE_STACK], [0], [use heap (malloc/free)]),
    AC_DEFINE([INI_USE_STACK], [1], [use stack])
)

AC_ARG_ENABLE(
    stop-on-first-error,
    AS_HELP_STRING([--enable-stop-on-first-error],
    [enable stop parsing on first error]),
    AC_DEFINE([INI_STOP_ON_FIRST_ERROR], [1], [stop parsing on first error]),
    AC_DEFINE([INI_STOP_ON_FIRST_ERROR], [0], [keep parsing when error is found])
)

AC_ARG_VAR(COMMENT_PREFIXES, [valid inline comment characters])


# Checks for header files.
AC_CHECK_HEADERS([stdlib.h string.h])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_TYPE_SIZE_T

# Checks for library functions.
AC_FUNC_MALLOC
AC_FUNC_STRTOD
AC_CHECK_FUNCS([strchr strdup strtol])

AC_OUTPUT
