# $OpenBSD: Makefile,v 1.24 2016/09/11 16:30:11 ratchov Exp $

COMMENT =	smalltalk system, vm

SRCV =		1
DISTFILES =	Squeak-$V-${SRCV}.src.tar.gz

PKGNAME =	squeak-vm-$V.${SRCV}
REVISION =	7

WRKDIST =	${WRKDIR}/Squeak-$V-${SRCV}
WRKSRC =	${WRKDIST}/platforms/unix/config

SEPARATE_BUILD =	Yes

MASTER_SITES =	${SQUEAK_SITE}unix-linux/

RUN_DEPENDS =		squeak-sources-${SOURCEV}:lang/squeak/sources

CONFIGURE_STYLE =	gnu
AUTOCONF_VERSION =	2.60
DESTDIRNAME =		ROOT
CONFIGURE_ENV =		LDFLAGS="-lpthread ${LDFLAGS}" RANLIB=ranlib \
			ac_cv_socklen_t=yes
USE_GMAKE =		Yes
USE_LIBTOOL =		No
NO_TEST =		Yes

WANTLIB =		GL X11 m c SM util Xext ICE Xrender Xt pthread \
			pthread-stubs xcb
FULLV =			$V-${SRCV}

# XXX gnu-interp doesn't work with pie.
#.if ${MACHINE_ARCH} != "powerpc"
#MAKE_FLAGS +=		INTERP=gnu-interp
#.endif

MAKE_FLAGS +=		docdir=${PREFIX}/share/doc/squeak
DESTDIRNAME =		ROOT
SUBST_VARS +=		FULLV

pre-build:
	@perl -pi -e s,dprintf,debugprintf, ${WRKDIST}/platforms/unix/vm/*.c
	@perl -pi -e s,"define dprintf","define debugprintf", ${WRKDIST}/platforms/unix/vm/debug.h

.include <bsd.port.mk>
