# $OpenBSD: Makefile,v 1.3 2015/10/23 15:27:16 feinerer Exp $

COMMENT =		OpenGL to PostScript printing library

DISTNAME =		gl2ps-1.3.9

SHARED_LIBS =		gl2ps	0.0 # 1.3

CATEGORIES =		print

HOMEPAGE =		http://www.geuz.org/gl2ps/

MAINTAINER =		Ingo Feinerer <feinerer@logic.at>

# LGPLv2
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB =		GL GLU Xi Xmu glut m png z

MASTER_SITES =		http://geuz.org/gl2ps/src/

EXTRACT_SUFX =		.tgz

MODULES =		devel/cmake
BUILD_DEPENDS =		print/texlive/base
LIB_DEPENDS =		graphics/freeglut \
			graphics/png

TEST_IS_INTERACTIVE =	x11

WRKSRC =		${WRKDIR}/${DISTNAME}-source

TEST_TMP=${WRKDIR}/test_tmp
do-test:
	mkdir -p ${TEST_TMP}
	${CC} -I${LOCALBASE}/include -I${X11BASE}/include \
	      -L${LOCALBASE}/lib -L${X11BASE}/lib -L${WRKBUILD} \
	      -lgl2ps -lglut -lGL -lGLU -lX11 -lm \
	      ${WRKSRC}/gl2psTestSimple.c -o ${TEST_TMP}/gl2psTestSimple
	${CC} -I${LOCALBASE}/include -I${X11BASE}/include \
	      -L${LOCALBASE}/lib -L${X11BASE}/lib -L${WRKBUILD} \
	      -lgl2ps -lglut -lGL -lGLU -lX11 -lm \
	      -DHAVE_LIBPNG -DHAVE_ZLIB -lpng -lz \
	      ${WRKSRC}/gl2psTest.c -o ${TEST_TMP}/gl2psTest
	cd ${TEST_TMP} && LD_LIBRARY_PATH=${WRKBUILD} ${TEST_TMP}/gl2psTestSimple
	cd ${TEST_TMP} && LD_LIBRARY_PATH=${WRKBUILD} ${TEST_TMP}/gl2psTest

.include <bsd.port.mk>
