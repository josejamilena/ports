# $OpenBSD: Makefile,v 1.20 2016/03/11 19:59:15 naddy Exp $

COMMENT=	GUI widget library used in MakeHuman

DISTNAME=	mhgui-0.2
CATEGORIES=	graphics
REVISION=	3

SHARED_LIBS +=  mhgui                1.0      # unknown

HOMEPAGE=	http://www.dedalo-3d.com/

# LGPLv2.1
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += GL GLU ICE SM X11 Xdamage Xext Xfixes Xi Xmu Xt Xxf86vm
WANTLIB += animorph drm glut m png stdc++ xcb z
WANTLIB += X11-xcb Xrandr Xrender glapi pthread
WANTLIB += usbhid xcb-dri2 xcb-glx expat

MASTER_SITES=	${MASTER_SITE_SOURCEFORGE:=makehuman/}

LIB_DEPENDS=	graphics/animorph>=0.3 \
		graphics/freeglut \
		graphics/png

CONFIGURE_STYLE=gnu
CONFIGURE_ENV=	CPPFLAGS="-I${LOCALBASE}/include -I${LOCALBASE}/include/GL" \
		LDFLAGS="-L${LOCALBASE}/lib -lz -lm"

# remove useless files (ChangeLog, INSTALL...)
post-install:
	rm -r ${PREFIX}/share/doc

.include <bsd.port.mk>
