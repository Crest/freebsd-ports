# $FreeBSD$

PORTNAME=	case-insensitive
PORTVERSION=	1.2.0.11
PORTREVISION=	2
CATEGORIES=	textproc haskell

MAINTAINER=	haskell@FreeBSD.org
COMMENT=	Case-insensitive string comparison

LICENSE=	BSD3CLAUSE

DEPRECATED=		Haskell libraries are getting pushed out of the ports tree. If you are using this port for development, consider switching to cabal sandboxes (old way), cabal new-build (new way), or use devel/stack. If you believe this port shouldn't be removed, contact haskell@FreeBSD.org
EXPIRATION_DATE=	2019-04-14

USE_CABAL=	hashable>=1.0

.include "${.CURDIR}/../../lang/ghc/bsd.cabal.mk"
.include <bsd.port.mk>
