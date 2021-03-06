dnl Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([GtkShot], [2.0], [crazydan0@126.com])
AM_INIT_AUTOMAKE([1.11 no-dist-gzip dist-xz tar-ustar])
AC_CONFIG_SRCDIR([src/main.c])
AC_CONFIG_HEADERS([config.h])

AM_MAINTAINER_MODE([enable])
AM_SILENT_RULES([yes])

# Checks for programs.
AC_LANG_C
AM_PROG_LIBTOOL

AC_ISC_POSIX
AC_PROG_CC
AM_PROG_CC_STDC
AM_PROG_CC_C_O
AC_HEADER_STDC
AC_PATH_PROG(GLIB_COMPILE_RESOURCES, glib-compile-resources)

# Checks for libraries.
GTK3_REQUIRED=3.8.2
GTK2_REQUIRED=2.12.0
PKG_CHECK_MODULES(GTK, gtk+-2.0 >= $GTK2_REQUIRED)
AC_SUBST(GTK_CFLAGS)
AC_SUBST(GTK_LIBS)

pkg_modules="x11"
PKG_CHECK_MODULES(X11, [$pkg_modules])
AC_SUBST(X11_CFLAGS)
AC_SUBST(X11_LIBS)


dnl dnl
ALL_LINGUAS="en_US zh_CN zh_TW"
AM_GLIB_GNU_GETTEXT
IT_PROG_INTLTOOL([0.40.0])

AC_DEFINE([GTK_SHOT_NAME], ["@S|@{PACKAGE_NAME}"], [The name of programme])
AC_DEFINE([GTK_SHOT_VERSION], ["@S|@{PACKAGE_VERSION}"], [The version of programme])
AC_DEFINE([SYSTEM_CURSOR_SIZE], [16], [The size of cursor])

AC_ARG_ENABLE(debug,
              AC_HELP_STRING([--enable-debug], [enable to print debug information]),
              [case "${enableval}" in
                yes) enable_debug = yes ;;
                no) enable_debug = no ;;
                *) AC_MSG_ERROR([bad value "${enableval}" for --enable-debug, use "yes" (default) or "no".]) ;;
               esac], [enable_debug=no])
if test "x$enable_debug" = "xyes" ; then
  AC_DEFINE([GTK_SHOT_DEBUG], [], [Print debug information when programme is running])
fi


GETTEXT_PACKAGE=gtkshot
AC_SUBST(GETTEXT_PACKAGE)
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE", [Gettext package.])

AC_OUTPUT([
Makefile
src/Makefile
po/Makefile.in
])

echo
echo $PACKAGE_NAME....................... : Version $PACKAGE_VERSION
echo Prefix..........................: $prefix
echo The binary will be installed in $prefix/bin
echo http://crazydan.org/

