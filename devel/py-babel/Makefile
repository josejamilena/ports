# $OpenBSD: Makefile,v 1.21 2016/11/10 21:58:40 danj Exp $

COMMENT=		I18N/L10N tools for Python

MODPY_EGG_VERSION=	2.3.4
DISTNAME=		Babel-${MODPY_EGG_VERSION}
PKGNAME=		py-${DISTNAME:L}
CATEGORIES=    		devel

HOMEPAGE=		http://babel.pocoo.org/

MAINTAINER =		Alexandr Shadchin <shadchin@openbsd.org>

# BSD
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python

MODPY_PI =		Yes
MODPY_SETUPTOOLS=	Yes

RUN_DEPENDS=		devel/py-tz${MODPY_FLAVOR}
TEST_DEPENDS=		${RUN_DEPENDS} \
			devel/py-test${MODPY_FLAVOR}

FLAVORS=		python3
FLAVOR?=

post-install:
	mv ${PREFIX}/bin/pybabel \
		${PREFIX}/bin/pybabel${MODPY_BIN_SUFFIX}

do-test:
	cd ${WRKSRC} && ${MODPY_BIN} -m pytest

.include <bsd.port.mk>
