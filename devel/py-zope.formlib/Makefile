# $FreeBSD$

PORTNAME=	zope.formlib
PORTVERSION=	4.3.0
CATEGORIES=	devel python zope
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}
DIST_SUBDIR=	zope

MAINTAINER=	zope@FreeBSD.org
COMMENT=	Form generation and validation library for Zope

LICENSE=	ZPL21
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}pytz>=0:devel/py-pytz@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.browser>=1.1:devel/py-zope.browser@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.browserpage>=3.11.0:devel/py-zope.browserpage@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.component>=0:devel/py-zope.component@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.event>=0:devel/py-zope.event@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.i18n>=0:devel/py-zope.i18n@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.i18nmessageid>=0:textproc/py-zope.i18nmessageid@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.interface>=0:devel/py-zope.interface@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.lifecycleevent>=0:devel/py-zope.lifecycleevent@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.publisher>=0:devel/py-zope.publisher@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.schema>=3.5.1:devel/py-zope.schema@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.security>=0:security/py-zope.security@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.traversing>=0:devel/py-zope.traversing@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}zope.datetime>=0:devel/py-zope.datetime@${PY_FLAVOR}

NO_ARCH=	yes
USES=		python:2.7
USE_PYTHON=	autoplist distutils

.include <bsd.port.mk>
