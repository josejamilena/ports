# $OpenBSD: Makefile,v 1.22 2016/10/31 09:48:22 jasper Exp $

COMMENT=		font viewer for GNOME

GNOME_PROJECT=		gnome-font-viewer
GNOME_VERSION=		3.22.0

# GPLv2
PERMIT_PACKAGE_CDROM=	Yes

WANTLIB += ICE SM X11 Xcomposite Xcursor Xdamage Xext Xfixes Xi
WANTLIB += Xinerama Xrandr Xrender atk-1.0 atk-bridge-2.0 atspi
WANTLIB += c cairo cairo-gobject dbus-1 expat ffi fontconfig freetype
WANTLIB += gdk-3 gdk_pixbuf-2.0 gio-2.0 glib-2.0 gmodule-2.0 gnome-desktop-3
WANTLIB += gobject-2.0 graphite2 gthread-2.0 gtk-3 harfbuzz
WANTLIB += m pango-1.0 pangocairo-1.0 pangoft2-1.0 epoxy
WANTLIB += pcre pixman-1 png pthread pthread-stubs xcb xcb-render
WANTLIB += xcb-shm z iconv intl

LIB_DEPENDS=		x11/gnome/desktop

MODULES=		x11/gnome

MODGNOME_TOOLS +=	desktop-file-utils

.include <bsd.port.mk>
