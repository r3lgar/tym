#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

m4_define([tym_major_version],[1])
m4_define([tym_minor_version],[0])
m4_define([tym_micro_version],[8])
m4_define([tym_version],[tym_major_version().tym_minor_version().tym_micro_version()])

AC_PREREQ([2.69])
AC_INIT([tym], [tym_version()], [], [tym], [https://github.com/endaaman/tym])
AM_INIT_AUTOMAKE([foreign])
AC_CONFIG_SRCDIR([src/tym.c])
AC_CONFIG_HEADERS([config.h:config.h.in])
AC_CONFIG_FILES([
  Makefile
  src/Makefile
])

AC_ARG_ENABLE(debug,
[  --enable-debug          turn on debugging [[default=no]]],
[\
case "${enableval}" in
 yes) enable_debug=yes ;;
 no)  enable_debug=no ;;
 *)   AC_MSG_ERROR(bad value for --enable-debug) ;;
esac],
enable_debug=no)
if test x"${enable_debug}" = x"yes"; then
  AC_DEFINE(DEBUG, 1, [Define to 1 if you want to debug])
fi
AM_CONDITIONAL(DEBUG, test x"$debug" = x"true")

AC_PROG_CC

PKG_PROG_PKG_CONFIG
PKG_CHECK_MODULES(TYM, [gtk+-3.0 vte-2.91 lua53 ])

AC_OUTPUT
