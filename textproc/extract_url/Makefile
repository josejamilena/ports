# $OpenBSD: Makefile,v 1.1.1.1 2016/01/06 17:53:37 feinerer Exp $

COMMENT =		extract URLs from MIME email messages or plain text

VERSION =		1.6
DISTNAME =		extract_url-${VERSION}

CATEGORIES =		textproc

HOMEPAGE =		http://www.memoryhole.net/~kyle/extract_url/

MAINTAINER =		Ingo Feinerer <feinerer@logic.at>

# BSD
PERMIT_PACKAGE_CDROM =	Yes

GH_ACCOUNT =		m3m0ryh0l3
GH_PROJECT =		extracturl
GH_TAGNAME =		v${VERSION}

BUILD_DEPENDS =		mail/p5-MIME-tools \
			www/p5-HTML-Parser
RUN_DEPENDS =		devel/p5-Curses-UI \
			mail/p5-MIME-tools \
			www/p5-HTML-Parser \
			www/p5-URI-Find

FAKE_FLAGS =		man_prefix=${PREFIX} \
			prefix=${PREFIX}

USE_GMAKE =		Yes

post-patch:
	sed -i "/pod2man.mk/s/make/${GMAKE}/" ${WRKSRC}/Makefile
	sed -i "s/extract_url.pl/extract_url/g" ${WRKSRC}/extract_url.pl

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/extract_url
	${INSTALL_DATA} ${WRKSRC}/extract_urlview.sample \
		${PREFIX}/share/examples/extract_url

.include <bsd.port.mk>
