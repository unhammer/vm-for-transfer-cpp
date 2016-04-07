#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ(2.52)

m4_define([required_lttoolbox_version], [3.3.1])
m4_define([required_libxml_version], [2.6.17])

AC_INIT([Apertium Transfer VM], [0.1.0], [Andrei Sfrent <andrei@asfrent.net>], [apertium-transfer-vm], [http://wiki.apertium.org/wiki/VM_for_transfer])
AM_INIT_AUTOMAKE

dnl AC_CONFIG_HEADER([apertium/apertium_config.h])

dnl AC_CANONICAL_SYSTEM

dnl GENERIC_LIBRARY_NAME=apertium

dnl # Release versioning
dnl GENERIC_MAJOR_VERSION=3
dnl GENERIC_MINOR_VERSION=4
dnl GENERIC_MICRO_VERSION=0

dnl # API version (often = GENERIC_MAJOR_VERSION.GENERIC_MINOR_VERSION)
dnl GENERIC_API_VERSION=$GENERIC_MAJOR_VERSION.$GENERIC_MINOR_VERSION
dnl AC_SUBST(GENERIC_API_VERSION)
dnl AC_SUBST(GENERIC_MAJOR_VERSION)

dnl # Shared library versioning
dnl GENERIC_LIBRARY_VERSION=0:0:0
dnl #                       | | |
dnl #                +------+ | +---+
dnl #                |        |     |
dnl #             current:revision:age
dnl #                |        |     |
dnl #                |        |     +- increment if interfaces have been added
dnl #                |        |        set to zero if interfaces have been removed
dnl #                                  or changed
dnl #                |        +- increment if source code has changed
dnl #                |           set to zero if current is incremented
dnl #                +- increment if interfaces have been added, removed or changed

dnl AC_SUBST(GENERIC_LIBRARY_VERSION)
dnl PACKAGE=$GENERIC_LIBRARY_NAME
dnl AC_SUBST(GENERIC_LIBRARY_NAME)

dnl GENERIC_VERSION=$GENERIC_MAJOR_VERSION.$GENERIC_MINOR_VERSION.$GENERIC_MICRO_VERSION
dnl GENERIC_RELEASE=$GENERIC_MAJOR_VERSION.$GENERIC_MINOR_VERSION
dnl AC_SUBST(GENERIC_RELEASE)
dnl AC_SUBST(GENERIC_VERSION)

dnl VERSION=$GENERIC_VERSION

dnl AM_INIT_AUTOMAKE(no-define)

AC_PROG_CXX
AC_PROG_LIBTOOL
AM_SANITY_CHECK
AC_LANG_CPLUSPLUS

CFLAGS="-Wall -Wextra $CFLAGS"
CXXFLAGS="-std=c++11 -Wall -Wextra $CXXFLAGS"

AC_PATH_PROG([PKGCONFIG], [pkg-config], [false], [$PATH$PATH_SEPARATOR$with_pkg_config/bin])
AS_IF([test x$PKGCONFIG = xfalse], [AC_MSG_ERROR([You don't have pkg-config installed])])


PKG_CHECK_MODULES(APERTIUM_TRANSFER_VM, [
  lttoolbox >= required_lttoolbox_version
  libxml-2.0 >= required_libxml_version], CPPFLAGS="$CPPFLAGS $APERTIUM_TRANSFER_VM_CFLAGS"; LIBS="$LIBS $APERTIUM_TRANSFER_VM_LIBS")

AC_OUTPUT([Makefile])
