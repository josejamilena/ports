# $OpenBSD: Makefile,v 1.6 2015/01/21 06:13:48 bentley Exp $

COMMENT=	decision procedure for bit-vectors and arrays

V=		0.1
DISTNAME=	stp-ver-${V}-11-18-2008
PKGNAME=	stp-${V}
REVISION=	1

CATEGORIES=	devel

HOMEPAGE=	https://sites.google.com/site/stpfastprover/STP-Fast-Prover

# MIT license
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB=	c m stdc++

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=stp-fast-prover/}
EXTRACT_SUFX=	.tgz

BUILD_DEPENDS=	devel/bison

MAKE_ENV=	CXX="${CXX}"

USE_GMAKE=	Yes
CONFIGURE_STYLE= simple

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/include/stp
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/stp
	${INSTALL_PROGRAM} ${WRKSRC}/bin/stp ${PREFIX}/bin
	${INSTALL_DATA} ${WRKSRC}/lib/libstp.a ${PREFIX}/lib
	${INSTALL_DATA} ${WRKSRC}/c_interface/*.h ${PREFIX}/include/stp
	${INSTALL_DATA} ${WRKSRC}/PAPERS/*.pdf ${PREFIX}/share/doc/stp

.include <bsd.port.mk>
