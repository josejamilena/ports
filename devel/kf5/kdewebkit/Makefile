# $OpenBSD: Makefile,v 1.2 2016/06/19 20:03:59 sthen Exp $

COMMENT =	integration of the HTML rendering engine WebKit into KDE
DISTNAME =	kdewebkit-${VERSION}

SHARED_LIBS =	KF5WebKit		0.0

WANTLIB =  KF5Auth KF5Codecs KF5Completion KF5ConfigCore KF5ConfigGui
WANTLIB += KF5ConfigWidgets KF5CoreAddons KF5I18n KF5JobWidgets
WANTLIB += KF5KIOCore KF5KIOWidgets KF5Parts KF5Service KF5SonnetUi
WANTLIB += KF5TextWidgets KF5Wallet KF5WidgetsAddons KF5XmlGui
WANTLIB += Qt5Core Qt5DBus Qt5Gui Qt5Network Qt5WebKit Qt5WebKitWidgets
WANTLIB += Qt5Widgets Qt5Xml m

LIB_DEPENDS =	devel/kf5/kconfig \
		devel/kf5/kcoreaddons \
		devel/kf5/kjobwidgets \
		devel/kf5/kio \
		devel/kf5/kparts \
		devel/kf5/kservice \
		devel/kf5/kwallet

BUILD_DEPENDS =	devel/gettext-tools

.include <bsd.port.mk>
