# $OpenBSD: Makefile,v 1.7 2016/11/04 11:35:20 sthen Exp $

CATEGORIES =		productivity devel
COMMENT =		C library for Google calendar and contacts
DISTNAME =		libgcal-0.9.6
HOMEPAGE =		https://code.google.com/p/libgcal/
REVISION =		3

SHARED_LIBS =		gcal	0.0

# BSDL
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += crypto curl lzma m nghttp2 pthread ssl xml2 z

MASTER_SITES =		${MASTER_SITE_GOOGLECODE:=libgcal/}
EXTRACT_SUFX =		.tar.bz2

CONFIGURE_STYLE =	gnu

MODULES =		devel/gettext
BUILD_DEPENDS =		devel/check
LIB_DEPENDS =		net/curl \
			textproc/libxml

SEPARATE_BUILD =	Yes

.include <bsd.port.mk>
