AC_INIT([enigma2-oe-alliance-plugins],[1.0])
AM_INIT_AUTOMAKE([dist-bzip2 foreign no-define tar-pax])
AC_CONFIG_HEADERS([enigma2-plugins-config.h])

# Silent rules are available since 1.11, but older versions
# are still in use. So don't use them unconditionally.
m4_ifdef([AM_SILENT_RULES], [AM_SILENT_RULES([yes])])

AC_USE_SYSTEM_EXTENSIONS
AC_SYS_LARGEFILE

AC_PROG_CC
AC_PROG_CXX
m4_ifdef([LT_INIT], [LT_INIT], [AC_PROG_LIBTOOL])
AC_CONFIG_MACRO_DIR([m4])

AC_CHECK_HEADERS([dbox/fp.h dbox/lcd-ks0713.h])

AC_PATH_PROG(MSGFMT, msgfmt, AC_MSG_ERROR(Could not find msgfmt))
AC_PATH_PROG(MSGINIT, msginit, AC_MSG_ERROR(Could not find msginit))
AC_PATH_PROG(MSGMERGE, msgmerge, AC_MSG_ERROR(Could not find msgmerge))
AC_PATH_PROG(MSGUNIQ, msguniq, AC_MSG_ERROR(Could not find msguniq))
AC_PATH_PROG(XGETTEXT, xgettext, AC_MSG_ERROR(Could not find xgettext))

AM_PATH_PYTHON
AX_PYTHON_DEVEL
AX_PTHREAD

AC_ARG_WITH(boxtype,
	[  --with-boxtype=NAME box type [[none,dm7025,dm800...]]],
	[BOXTYPE="$withval"],[BOXTYPE="dm800"])
AC_SUBST(BOXTYPE)
AC_DEFINE_UNQUOTED(BOXTYPE,"$BOXTYPE",[box type])

AM_CONDITIONAL(AZBOX, test `echo "$BOXTYPE" | cut -b 1-5` == "azbox")
AM_CONDITIONAL(CUBE, test `echo "$BOXTYPE" | cut -b 1-4` == "cube")
AM_CONDITIONAL(DAGS, test `echo "$BOXTYPE" | cut -b 1-4` == "dags")
AM_CONDITIONAL(DREAMBOX, test `echo "$BOXTYPE" | cut -b 1-2` == "dm")
AM_CONDITIONAL(VUPLUS, test `echo "$BOXTYPE" | cut -b 1-2` == "vu")
AM_CONDITIONAL(XTREND, test `echo "$BOXTYPE" | cut -b 1-2` == "et")
AM_CONDITIONAL(INI, test `echo "$BOXTYPE" | cut -b 1-3` == "ini")
AM_CONDITIONAL(GIGABLUE, test `echo "$BOXTYPE" | cut -b 1-2` == "gb")
AM_CONDITIONAL(ODIN, test `echo "$BOXTYPE" | cut -b 1-4` == "odin")
AM_CONDITIONAL(EBOX, test `echo "$BOXTYPE" | cut -b 1-4` == "ebox")

AM_CONDITIONAL(AZBOXHD, test "$BOXTYPE" == "azboxhd")
AM_CONDITIONAL(AZBOXME, test "$BOXTYPE" == "azboxme")
AM_CONDITIONAL(AZBOXMINIME, test "$BOXTYPE" == "azboxminime")
AM_CONDITIONAL(BLACKBOX7405, test "$BOXTYPE" == "blackbox7405")
AM_CONDITIONAL(CUBE, test "$BOXTYPE" == "cube")
AM_CONDITIONAL(DAGS1, test "$BOXTYPE" == "dags1")
AM_CONDITIONAL(DAGS2, test "$BOXTYPE" == "dags2")
AM_CONDITIONAL(DAGS3, test "$BOXTYPE" == "dags3")
AM_CONDITIONAL(DM500HD, test "$BOXTYPE" == "dm500hd")
AM_CONDITIONAL(DM500HDV2, test "$BOXTYPE" == "dm500hdv2")
AM_CONDITIONAL(DM800, test "$BOXTYPE" == "dm800")
AM_CONDITIONAL(DM800SE, test "$BOXTYPE" == "dm800se")
AM_CONDITIONAL(DM800SEV2, test "$BOXTYPE" == "dm800sev2")
AM_CONDITIONAL(DM7020HD, test "$BOXTYPE" == "dm7020hd")
AM_CONDITIONAL(DM7020HDV2, test "$BOXTYPE" == "dm7020hdv2")
AM_CONDITIONAL(DM8000, test "$BOXTYPE" == "dm8000")
AM_CONDITIONAL(E3HD, test "$BOXTYPE" == "e3hd")
AM_CONDITIONAL(EBOX5000, test "$BOXTYPE" == "ebox5000")
AM_CONDITIONAL(EBOX5100, test "$BOXTYPE" == "ebox5100")
AM_CONDITIONAL(EBOX7358, test "$BOXTYPE" == "ebox7358")
AM_CONDITIONAL(EBOXLUMI, test "$BOXTYPE" == "eboxlumi")
AM_CONDITIONAL(ET4X00, test "$BOXTYPE" == "et4x00")
AM_CONDITIONAL(ET5X00, test "$BOXTYPE" == "et5x00")
AM_CONDITIONAL(ET6X00, test "$BOXTYPE" == "et6x00")
AM_CONDITIONAL(ET9X00, test "$BOXTYPE" == "et9x00")
AM_CONDITIONAL(ET8000, test "$BOXTYPE" == "et8000")
AM_CONDITIONAL(ET10000, test "$BOXTYPE" == "et10000")
AM_CONDITIONAL(EW7358, test `echo "$BOXTYPE"` == "ew7358")
AM_CONDITIONAL(GB800SOLO, test "$BOXTYPE" == "gb800solo")
AM_CONDITIONAL(GB800SE, test "$BOXTYPE" == "gb800se")
AM_CONDITIONAL(GB800UE, test "$BOXTYPE" == "gb800ue")
AM_CONDITIONAL(GB800SEPLUS, test "$BOXTYPE" == "gb800seplus")
AM_CONDITIONAL(GB800UEPLUS, test "$BOXTYPE" == "gb800ueplus")
AM_CONDITIONAL(GBQUADPLUS, test "$BOXTYPE" == "gbquadplus")
AM_CONDITIONAL(GBQUAD, test "$BOXTYPE" == "gbquad")
AM_CONDITIONAL(INIHDE, test "$BOXTYPE" == "inihde")
AM_CONDITIONAL(INIHDE2, test "$BOXTYPE" == "inihde2")
AM_CONDITIONAL(INIHDP, test "$BOXTYPE" == "inihdp")
AM_CONDITIONAL(INIHDX, test "$BOXTYPE" == "inihdx")
AM_CONDITIONAL(IXUSSZERO, test "$BOXTYPE" == "ixusszero")
AM_CONDITIONAL(IXUSSONE, test "$BOXTYPE" == "ixussone")
AM_CONDITIONAL(MUTANT2400, test "$BOXTYPE" == "mutant2400")
AM_CONDITIONAL(ODINM7, test "$BOXTYPE" == odinm7)
AM_CONDITIONAL(ODINM7S, test "$BOXTYPE" == odinm7s)
AM_CONDITIONAL(ODINM7C, test "$BOXTYPE" == odinm7c)
AM_CONDITIONAL(ODINM9, test "$BOXTYPE" == odinm9)
AM_CONDITIONAL(VUUNO, test "$BOXTYPE" == vuuno)
AM_CONDITIONAL(VUULTIMO, test "$BOXTYPE" == vuultimo)
AM_CONDITIONAL(VUSOLO, test "$BOXTYPE" == vusolo)
AM_CONDITIONAL(VUSOLOSE, test "$BOXTYPE" == vusolose)
AM_CONDITIONAL(VUDUO, test "$BOXTYPE" == vuduo)
AM_CONDITIONAL(VUSOLO2, test "$BOXTYPE" == vusolo2)
AM_CONDITIONAL(VUDUO2, test "$BOXTYPE" == vuduo2)
AM_CONDITIONAL(XP1000, test "$BOXTYPE" == xp1000)

AM_CONDITIONAL(HAVE_TEMPFANCONTROL, test "$BOXTYPE" == dm8000 -o "$BOXTYPE" == dm800se -o "$BOXTYPE" == dm500hd -o "$BOXTYPE" == vuuno -o "$BOXTYPE" == vuultimo -o "$BOXTYPE" == vusolo2 -o "$BOXTYPE" == vuduo2 -o "$BOXTYPE" == tmsingle -o "$BOXTYPE" == tmtwin -o "$BOXTYPE" == tm2t -o "$BOXTYPE" == tmnano -o "$BOXTYPE" == iqonios100hd -o "$BOXTYPE" == iqonios200hd -o "$BOXTYPE" == iqonios300hd -o "$BOXTYPE" == optimussos1 -o "$BOXTYPE" == optimussos2 -o "$BOXTYPE" == dags1 -o "$BOXTYPE" == dags2 -o "$BOXTYPE" == dags3)
AM_CONDITIONAL(HAVE_WIRELESSACCESSPOINT, test "$BOXTYPE" != cube)

AC_CONFIG_FILES([
Makefile

TransCodingSetup/Makefile
TransCodingSetup/src/Makefile
TransCodingSetup/meta/Makefile
TransCodingSetup/po/Makefile

])
AC_OUTPUT
