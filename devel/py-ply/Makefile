# $OpenBSD: Makefile,v 1.2 2016/10/07 10:29:34 sthen Exp $

COMMENT =		Python lex/yacc

MODPY_EGG_VERSION =	3.9
DISTNAME =		ply-${MODPY_EGG_VERSION}
PKGNAME =		py-${DISTNAME}
CATEGORIES =		devel

HOMEPAGE =		http://www.dabeaz.com/ply/

# BSD
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		lang/python

MODPY_PI =		Yes
MODPY_SETUPTOOLS =	Yes

FLAVORS =		python3
FLAVOR ?=

do-test:
	cd ${WRKSRC}/test && \
	    ${MODPY_BIN} testlex.py && \
	    ${MODPY_BIN} testyacc.py

.include <bsd.port.mk>
