# $OpenBSD: Makefile,v 1.1.1.1 2016/08/02 16:47:12 feinerer Exp $

COMMENT =	command line XML toolkit

DISTNAME =	xmlstarlet-1.6.1

CATEGORIES =	textproc

HOMEPAGE =	http://xmlstar.sourceforge.net/

MAINTAINER =		Ingo Feinerer <feinerer@logic.at>

# MIT
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB += c exslt xml2 xslt

MASTER_SITES =		${MASTER_SITE_SOURCEFORGE:=xmlstar/}

LIB_DEPENDS =		textproc/libxml \
			textproc/libxslt

CONFIGURE_STYLE =	gnu

post-install:
	${INSTALL_DATA} ${WRKSRC}/COPYING ${PREFIX}/share/doc/xmlstarlet

.include <bsd.port.mk>
