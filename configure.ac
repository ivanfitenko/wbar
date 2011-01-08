dnl make yadickson soto

AC_INIT(wbar, 2.0.1)
AM_INIT_AUTOMAKE(AC_PACKAGE_NAME, AC_PACKAGE_VERSION)

AM_CONFIG_HEADER(config.h)
AC_CONFIG_MACRO_DIR([m4])

AC_PROG_CXX
AC_PROG_INSTALL
AC_HEADER_STDC

eval "prefix=$prefix"
eval "exec_prefix=$exec_prefix"
eval "libdir=$libdir"
eval "bindir=$bindir"
eval "datadir=$datadir"
eval "localedir=$localedir"
eval "sysconfdir=$sysconfdir"

LIBDIR=`eval echo $libdir`
BINDIR=`eval echo $bindir`
SHARE_DATADIR=`eval echo $datadir`
LOCALEDIR=`eval echo $localedir`
SYSCONFDIR=`eval echo $sysconfdir`

AC_SUBST(LIBDIR)
AC_SUBST(BINDIR)
AC_SUBST(SYSCONFDIR)

AC_SUBST(GETTEXT_PACKAGE, [AC_PACKAGE_NAME])
AC_DEFINE_UNQUOTED(GETTEXT_PACKAGE, "$GETTEXT_PACKAGE" , [ The gettext package ])

AC_SUBST(GNOMELOCALEDIR, $LOCALEDIR)
AC_DEFINE_UNQUOTED(GNOMELOCALEDIR, "$GNOMELOCALEDIR" , [ The gettext package dir ])

AC_SUBST(DEFAULT_CONFIGDIR, "$SYSCONFDIR/default/AC_PACKAGE_NAME")
AC_DEFINE_UNQUOTED(DEFAULT_CONFIGDIR, "$DEFAULT_CONFIGDIR" , [ The default config dir ])

AC_SUBST(AUTOSTARTDIR, "$SYSCONFDIR/xdg/autostart")
AC_DEFINE_UNQUOTED(AUTOSTARTDIR, "$AUTOSTARTDIR" , [ The autostart dir ])

AC_SUBST(PIXMAPDIR, "$SHARE_DATADIR/pixmaps")
AC_DEFINE_UNQUOTED(PIXMAPDIR, "$PIXMAPDIR" , [ The pixmaps dir ])

AC_SUBST(GLADE_PACKAGE_DIR, "$SHARE_DATADIR/AC_PACKAGE_NAME/glade")
AC_DEFINE_UNQUOTED(GLADE_PACKAGE_DIR, "$GLADE_PACKAGE_DIR" , [ The glade package dir ])

AC_SUBST(GLADE_PACKAGE_NAME, "$GLADE_PACKAGE_DIR/AC_PACKAGE_NAME.glade")
AC_DEFINE_UNQUOTED(GLADE_PACKAGE_NAME, "$GLADE_PACKAGE_NAME" , [ The glade package name ])

AC_SUBST(DEFAULT_ARGV, "--bpress --above-desk --vbar --pos right --isize 32 --idist 5 --nanim 4 --falfa 65")
AC_DEFINE_UNQUOTED(DEFAULT_ARGV, "$DEFAULT_ARGV" , [ The default argv ])

AC_PROG_INTLTOOL()
AM_GLIB_GNU_GETTEXT
PKG_PROG_PKG_CONFIG

PKG_CHECK_MODULES(modules, [imlib2])
AC_SUBST(modules_CFLAGS)
AC_SUBST(modules_LIBS)

PKG_CHECK_MODULES(gui_modules, [gtk+-2.0 libglade-2.0])
AC_SUBST(gui_modules_CFLAGS)
AC_SUBST(gui_modules_LIBS)

CPPFLAGS="${CPPFLAGS} -Wall -Werror -g -O2"

AC_CONFIG_FILES([Makefile \
share/Makefile \
etc/Makefile \
etc/wbar.cfg \
etc/wbar.desktop.in \
pixmaps/Makefile \
po/Makefile.in \
src/Makefile])

AC_OUTPUT
