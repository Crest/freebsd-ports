# $FreeBSD$

PORTNAME=	khtml
DISTVERSION=	${KDE_FRAMEWORKS_VERSION}
PORTREVISION=	1
CATEGORIES=	www kde kde-frameworks

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KF5 KTHML rendering engine

LIB_DEPENDS=	libgif.so:graphics/giflib \
		libpng.so:graphics/png

USES=		cmake compiler:c++11-lib gettext gperf jpeg kde:5 \
		qt:5 tar:xz
USE_KDE=	archive auth bookmarks codecs completion config \
		configwidgets coreaddons ecm globalaccel i18n iconthemes \
		jobwidgets js kio notifications parts service sonnet \
		textwidgets wallet widgetsaddons windowsystem xmlgui
USE_QT=		buildtools_build core dbus gui network phonon4 \
		printsupport qmake_build widgets x11extras xml
USE_XORG=	ice sm x11 xext

.include <bsd.port.mk>
