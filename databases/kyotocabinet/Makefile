# $OpenBSD: Makefile,v 1.14 2016/09/01 10:53:26 jasper Exp $

BROKEN-arm=	undefined reference to `__sync_fetch_and_add_8'
BROKEN-hppa=	undefined reference to `__sync_fetch_and_add_8'
BROKEN-powerpc=	undefined reference to `__sync_fetch_and_add_8'

# requires C++ tr1 headers
NOT_FOR_ARCHS=		${GCC3_ARCHS}

COMMENT=	straightforward implementation of DBM

DISTNAME=	kyotocabinet-1.2.76
REVISION=	0

SHARED_LIBS +=	kyotocabinet 0.0 # 16.0

CATEGORIES=	databases

HOMEPAGE=	http://fallabs.com/kyotocabinet/

# GPLv3
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += c m pthread stdc++ z

MASTER_SITES=	${HOMEPAGE}pkg/

USE_GMAKE=	Yes

CONFIGURE_STYLE=gnu

# This FLAVOR should be used for local builds only and not added to
# bulks (i.e. _no_ entry in databases/Makefile); the reason is that it
# uses -march=native which cannot be guaranteed to work on a machine it
# was not compiled on.
FLAVORS=	optimized
FLAVOR?=

.if ${FLAVOR:Moptimized}
CONFIGURE_ARGS += --enable-opt
.else
CONFIGURE_ARGS += --disable-opt
# i386 still need some optimized instructions
# undefined reference to `__sync_bool_compare_and_swap_8' ...
.if ${MACHINE_ARCH} == "i386"
CXXFLAGS += -march=i586
.endif
.endif

pre-configure:
	${SUBST_CMD} ${WRKSRC}/{configure,Makefile.in}

.include <bsd.port.mk>
