# $OpenBSD: Makefile,v 1.35 2016/09/23 09:16:54 sthen Exp $

ONLY_FOR_ARCHS =	amd64 i386 powerpc sparc64 alpha
USE_WXNEEDED =		Yes

# XXX remember to bump www/conkeror because it has a symlink pointing to lib/xulrunner-${MOZILLA_VER}
MOZILLA_VERSION =	24.8.0esr
MOZILLA_BRANCH =	esr24
MOZILLA_PROJECT =	xulrunner
MOZILLA_DIST =		firefox
PKGSPEC-devel =		xulrunner-devel->=24.0,<31.0
PKGSPEC-main =		xulrunner->=24.0,<31.0
REVISION-main =		15
REVISION-devel =	11

SO_VERSION =		0.0
MOZILLA_LIBS =		mozgnome mozalloc xul

# necessary glue to build with the correct compiler after fx 17
MODULES +=		gcc4 lang/clang
MODGCC4_ARCHS =		powerpc sparc64 alpha i386 amd64
MODGCC4_LANGS =		c c++
MODCLANG_ARCHS =
MODCLANG_LANGS =	c c++

# to be able to link when building with clang on i386 or gcc on ppc
.if ${MACHINE_ARCH} == "i386" || ${MACHINE_ARCH} == "powerpc"
CONFIGURE_ARGS +=	--disable-debug-symbols
.endif

WANTLIB +=		kvm
RUN_DEPENDS-devel =	${PKGNAME-main}:${BASE_PKGPATH},-main

CONFIGURE_ENV +=	MOZ_OFFICIAL_BRANDING_DIRECTORY=browser/branding

post-install:
	#otherwise libxul.so ends up being 1GB in sdk/lib
	${STRIP} ${PREFIX}/lib/${MOZILLA_PROJECT}-devel-${MOZILLA_VER}/sdk/lib/libxul.so.${SO_VERSION}
	#avoid conflict with lang/spidermonkey
	mv ${PREFIX}/lib/pkgconfig/{mozilla,libxul}-js.pc
	# MOZ_ENABLE_SKIA_GPU is false on ppc (see configure.in:8041 / bug 849253)
	# manually install the header to avoir packaging hacks
.if ${MACHINE_ARCH} == "powerpc"
	${INSTALL_DATA} ${WRKSRC}/gfx/gl/GLContextSkia.h \
		${PREFIX}/include/${MOZILLA_PROJECT}-${MOZILLA_VER}
.endif

.include <bsd.port.mk>
