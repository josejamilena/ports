# $OpenBSD: Makefile,v 1.9 2016/01/12 13:19:37 ajacoutot Exp $

COMMENT=		handle HTML forms on the client side

MODPY_EGG_VERSION=	0.2.10
DISTNAME=		ClientForm-${MODPY_EGG_VERSION}
PKGNAME=		py-clientform-${MODPY_EGG_VERSION}
REVISION=		4

CATEGORIES=		www

HOMEPAGE=		http://wwwsearch.sourceforge.net/ClientForm/
MASTER_SITES=		${HOMEPAGE}src/

MAINTAINER=		Will Maier <willmaier@ml1.net>

# BSD-like or ZPL
PERMIT_PACKAGE_CDROM=	Yes

MODULES=		lang/python
MODPY_SETUPTOOLS=	Yes

post-install:
	${INSTALL_DATA_DIR} ${PREFIX}/share/doc/py-clientform
	${INSTALL_DATA_DIR} ${PREFIX}/share/examples/py-clientform
.for i in COPYING.txt COPYRIGHT.txt *.html
	${INSTALL_DATA} ${WRKSRC}/$i ${PREFIX}/share/doc/py-clientform
.endfor
	${INSTALL_DATA} ${WRKSRC}/examples/* ${PREFIX}/share/examples/py-clientform

.include <bsd.port.mk>
