# $OpenBSD: Makefile,v 1.3 2016/03/20 19:56:22 naddy Exp $

COMMENT =		object oriented File::Find replacement

VERSION =		0.2.7
DISTNAME =		File-Find-Object-v${VERSION}
PKGNAME =		p5-File-Find-Object-${VERSION}

CATEGORIES =		devel

MAINTAINER =		Alexander Bluhm <bluhm@openbsd.org>

# Perl
PERMIT_PACKAGE_CDROM =	Yes

MODULES =		cpan
PKG_ARCH =		*
RUN_DEPENDS =		devel/p5-Class-XSAccessor
TEST_DEPENDS =		devel/p5-Test-Pod \
			devel/p5-Test-Pod-Coverage

.include <bsd.port.mk>
