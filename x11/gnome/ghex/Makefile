# $OpenBSD: Makefile,v 1.66 2016/10/12 18:21:09 jasper Exp $

COMMENT=		binary editor

GNOME_PROJECT=		ghex
GNOME_VERSION=		3.18.3

SHARED_LIBS +=  gtkhex-3                  0.0 # 0.0

CATEGORIES=		sysutils editors

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ICE SM X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi Xinerama
WANTLIB += Xrandr Xrender atk-1.0 atk-bridge-2.0 atspi c cairo
WANTLIB += cairo-gobject dbus-1 epoxy expat ffi fontconfig freetype
WANTLIB += gailutil-3 gdk-3 gdk_pixbuf-2.0 gio-2.0 glib-2.0 gmodule-2.0
WANTLIB += gobject-2.0 graphite2 gthread-2.0 gtk-3 harfbuzz m pango-1.0
WANTLIB += pangocairo-1.0 pangoft2-1.0 pcre pixman-1 png pthread
WANTLIB += pthread-stubs xcb xcb-render xcb-shm z iconv intl

MODULES=		devel/dconf \
			x11/gnome

LIB_DEPENDS=		x11/gtk+3

MODGNOME_TOOLS= 	desktop-file-utils gtk-update-icon-cache yelp

.include <bsd.port.mk>
