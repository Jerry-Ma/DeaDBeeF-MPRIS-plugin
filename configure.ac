dnl Process this file with autoconf to produce a configure script.
AC_INIT([deadbeef], [2.1.5], [huangcongyu2006@gmail.com])
AC_CONFIG_HEADER(config.h)
AC_CONFIG_AUX_DIR([build-aux])
AM_INIT_AUTOMAKE([deadbeef], [2.1.5], [huangcongyu2006@gmail.com])

AC_USE_SYSTEM_EXTENSIONS
AC_PROG_CC
AC_PROG_CXX
AC_STDC_HEADERS

AC_CONFIG_MACRO_DIR([m4])
LT_INIT

AC_C_BIGENDIAN

PKG_PROG_PKG_CONFIG
PKG_CHECK_MODULES(GLIB_DEPS, glib-2.0)
PKG_CHECK_MODULES(GIO_DEPS, gio-2.0)
PKG_CHECK_MODULES(GTHREAD_DEPS, gthread-2.0)
MPRIS_LIBS="$GLIB_DEPS_LIBS $GIO_DEPS_LIBS $GTHREAD_DEPS_LIBS"
MPRIS_CFLAGS="$GLIB_DEPS_CFLAGS $GIO_DEPS_CFLAGS $GTHREAD_DEPS_CFLAGS"
AC_SUBST(MPRIS_LIBS)
AC_SUBST(MPRIS_CFLAGS)

dnl Search for deadbeef installation directory
AC_PREFIX_PROGRAM(deadbeef)
if test "x$prefix" != xNone; then
    PLUGIN_INST="$prefix/lib/deadbeef"
else
    dnl Use default if nothing is found:
    PLUGIN_INST="$ac_default_prefix/lib/deadbeef"
fi
AC_SUBST(PLUGIN_INST)

AC_CONFIG_FILES([Makefile test/Makefile])

AC_OUTPUT
