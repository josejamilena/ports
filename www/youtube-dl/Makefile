# $OpenBSD: Makefile,v 1.159 2016/10/13 11:54:54 pirofti Exp $

COMMENT =	CLI program to download videos from YouTube and other sites

VERSION =	2016.10.12
MODPY_EGG_VERSION =	${VERSION:S/.0/./g}

DISTNAME =	youtube-dl-${VERSION}
CATEGORIES =	www

HOMEPAGE =	http://rg3.github.io/youtube-dl/

MAINTAINER =	Paul Irofti <pirofti@openbsd.org>

# Public Domain
PERMIT_PACKAGE_CDROM =		Yes

MASTER_SITES =	https://yt-dl.org/downloads/${VERSION}/

MODULES =	lang/python

MODPY_SETUPTOOLS =	Yes

TEST_DEPENDS +=	devel/flake8 \
		devel/py-nose

do-test:
	cd ${WRKSRC} && ${MAKE_PROGRAM} ${TEST_TARGET}

PKG_ARCH =	*

WRKDIST =	${WRKDIR}/youtube-dl

.include <bsd.port.mk>
