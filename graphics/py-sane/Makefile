# $OpenBSD: Makefile,v 1.3 2016/04/03 07:56:27 ajacoutot Exp $

COMMENT=		Python SANE module

MODPY_EGG_VERSION=	2.8.2
DISTNAME=		Sane-${MODPY_EGG_VERSION}
DISTFILES=		${DISTNAME}{v${MODPY_EGG_VERSION}}.tar.gz
PKGNAME=		py-${DISTNAME:L}
CATEGORIES=		graphics

HOMEPAGE=		http://python-pillow.github.io/

# PIL Software License
# Permission to use, copy, modify and distribute freely.
PERMIT_PACKAGE_CDROM=   Yes

WANTLIB += pthread sane ${MODPY_WANTLIB}

MASTER_SITES=          https://github.com/python-pillow/Sane/archive/

FLAVORS=		python3
FLAVOR?=

MODULES=		lang/python
SUBST_VARS=		MODPY_SITEPKG

RUN_DEPENDS=		graphics/py-Pillow${MODPY_FLAVOR} \
			math/py-numpy${MODPY_FLAVOR}

LIB_DEPENDS=		${MODPY_LIB_DEPENDS} \
			graphics/sane-backends

pre-configure:
	${SUBST_CMD} ${WRKSRC}/setup.py

.include <bsd.port.mk>
