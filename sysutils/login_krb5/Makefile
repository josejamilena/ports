# $OpenBSD: Makefile,v 1.14 2016/09/07 13:48:49 ajacoutot Exp $

COMMENT=		authentication provider for KerberosV

GIT_PROJECT=		login_krb5
GIT_COMMIT=		97e345f

DISTNAME=		${GIT_COMMIT}
PKGNAME=		${GIT_PROJECT}-6.1.1

DIST_SUBDIR=		${GIT_PROJECT}
WRKDIST=		${WRKDIR}/${GIT_PROJECT}-${GIT_COMMIT}

CATEGORIES=		sysutils security

MAINTAINER=		Antoine Jacoutot <ajacoutot@openbsd.org>

HOMEPAGE=		http://repo.or.cz/login_krb5.git

# ISC
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c com_err crypto pthread util

MASTER_SITES=		http://repo.or.cz/login_krb5.git/snapshot/

MODULES=		security/heimdal

NO_TEST=		Yes

FAKE_FLAGS=		BINDIR=${PREFIX}/libexec/auth \
			MANDIR=${PREFIX}/man/man

pre-configure:
	sed -i 's,/usr/local,${LOCALBASE},g' \
		${WRKSRC}/Makefile.inc \
		${WRKSRC}/login_krb5-or-pwd/Makefile \
		${WRKSRC}/login_krb5/Makefile

.include <bsd.port.mk>
