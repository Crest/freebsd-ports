PORTNAME=	ucspi-proxy
PORTVERSION=	1.1
PORTREVISION=	1
CATEGORIES=	sysutils
MASTER_SITES=	http://untroubled.org/ucspi-proxy/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Proxy program for UCSPI servers and clients
WWW=		https://untroubled.org/ucspi-proxy/

LICENSE=	GPLv2

LIB_DEPENDS=	libbg.so:devel/bglibs

USES=		libtool:build libtool:ldflags
BGLIBS_LIB=	${LOCALBASE}/lib/bglibs
BGLIBS_INCLUDE=	${LOCALBASE}/include/bglibs

PLIST_FILES=	bin/ucspi-proxy bin/ucspi-proxy-log bin/ucspi-proxy-pop3 \
		bin/ucspi-proxy-imap bin/ucspi-proxy-http-xlate \
		share/man/man1/ucspi-proxy-http-xlate.1.gz \
		share/man/man1/ucspi-proxy.1.gz

do-configure:
	${ECHO_CMD} "${STAGEDIR}${PREFIX}/bin"     > ${WRKSRC}/conf-bin
	${ECHO_CMD} "${STAGEDIR}${PREFIX}/share/man"  > ${WRKSRC}/conf-man
	${ECHO_CMD} "${CC} ${CFLAGS}"   > ${WRKSRC}/conf-cc
	${ECHO_CMD} "${CC} ${STRIP} ${LDFLAGS}"  > ${WRKSRC}/conf-ld
	${ECHO_CMD} "${BGLIBS_INCLUDE}" > ${WRKSRC}/conf-bgincs
	${ECHO_CMD} "${BGLIBS_LIB}"     > ${WRKSRC}/conf-bglibs

.include <bsd.port.mk>
