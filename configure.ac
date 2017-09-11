#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([docker-rpi-alpine], [0.1], [bhuisgen@hbis.fr])
AM_INIT_AUTOMAKE([foreign])
AM_MAINTAINER_MODE
AM_EXTRA_RECURSIVE_TARGETS([build pull push])

# Checks for programs.
AC_PROG_INSTALL
AC_PROG_MAKE_SET

AC_CHECK_PROG(DOCKER, docker, yes, no)
if test x"$DOCKER" != x"yes" ; then
    AC_MSG_ERROR([required program 'docker' not found])
fi

# Checks for libraries.

# Checks for header files.

# Checks for typedefs, structures, and compiler characteristics.

# Checks for library functions.

AC_ARG_VAR(TAG, tag of docker images)
AC_MSG_CHECKING([tag of docker images])
if test "x${TAG}" = "x"; then
    AC_SUBST(TAG, latest)
fi
AC_MSG_RESULT([${TAG}])

AC_ARG_VAR(CLEAN_OPTIONS, clean options)
AC_ARG_VAR(BUILD_OPTIONS, build options)
AC_ARG_VAR(PULL_OPTIONS, pull options)
AC_ARG_VAR(PUSH_OPTIONS, push options)

AC_CONFIG_FILES([
    Makefile
    rpi-alpine-base/Makefile
    rpi-alpine-base-consul/Makefile
    rpi-alpine-build/Makefile
    rpi-alpine-build-make/Makefile
    rpi-alpine-build-python/Makefile
    rpi-alpine-consul/Makefile
    rpi-alpine-dnsmasq/Makefile
    rpi-alpine-fabric/Makefile
    rpi-alpine-hostapd/Makefile
    rpi-alpine-kivy/Makefile
    rpi-alpine-rng/Makefile
    rpi-alpine-zabbix-agent/Makefile
])

AC_OUTPUT
