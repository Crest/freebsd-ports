# Created by: thierry@pompo.net
# $FreeBSD$

PORTNAME=	med
DISTVERSION=	3.3.1
PORTREVISION=	2
CATEGORIES=	french science

MAINTAINER=	thierry@FreeBSD.org
COMMENT=	Modelisation et Echanges de Donnees

LICENSE=	GPLv3

BUILD_DEPENDS=	gsed:textproc/gsed
LIB_DEPENDS=	libhdf5-18.so:science/hdf5-18

OPTIONS_DEFINE=	DOCS EXAMPLES

USES=		fortran gmake libtool tk
USE_CXXSTD=	gnu++98
CFLAGS+=	-fPIC
CONFIGURE_ARGS=	--disable-python --with-hdf5=${LOCALBASE}	\
		--with-hdf5-include=${LOCALBASE}/include/hdf5-18
CONFIGURE_ENV=	WISH=${WISH} H5DUMP=h5dump-18
GNU_CONFIGURE=	yes
USE_LDCONFIG=	yes
TEST_WRKSRC=	${WRKSRC}/tests
TEST_TARGET=	check  # XXX: some fail
TEST_ENV=	${MAKE_ENV} HDF5_DISABLE_VERSION_CHECK=1

WRKSRC=		${WRKDIR}/${PORTNAME}-${PORTVERSION}

LIBVER=		1.9.1
PLIST_SUB+=	VE=${LIBVER}

PATCH_TK_SCRIPTS=	tools/mdump/xmdump2.in tools/mdump/xmdump3.in

DOC2FIX=	. dox gif html html.dox jpg png
TST2FIX=	c f

post-patch:
	@${REINPLACE_CMD} -e 's|<malloc\.h>|<stdlib.h>|' \
		${WRKSRC}/include/2.3.6/med_outils.h \
		${WRKSRC}/include/med_outils.h
.for dd in ${DOC2FIX}
	@${REINPLACE_CMD} -e 's|docdir = $$(datadir)/doc|docdir = @docdir@|'	\
		${WRKSRC}/doc/${dd}/Makefile.in
.endfor
.for dd in ${TST2FIX}
	@${FIND} ${WRKSRC}/tests -name Makefile.in | ${XARGS}	\
	${REINPLACE_CMD} -e 's|test${dd}dir = $$(bindir)/test|test${dd}dir = ${EXAMPLESDIR}/test|' \
			-e 's|unittestsdir = $$(bindir)/unit|unittestsdir = ${EXAMPLESDIR}/unit|' \
			-e 's|usescasesdir = $$(bindir)/uses|usescasesdir = ${EXAMPLESDIR}/uses|'
.endfor
	# ATM MED is only compatible with hdf5-18
	@${REINPLACE_CMD} -e 's|-lhdf5|-lhdf5-18|'  ${WRKSRC}/${CONFIGURE_SCRIPT}

post-patch-DOCS-off:
	@${REINPLACE_CMD} -e '/SUBDIRS/ s|doc||' ${WRKSRC}/Makefile.in

post-patch-EXAMPLES-off:
	@${REINPLACE_CMD} -e '/SUBDIRS/ s|tests||' ${WRKSRC}/Makefile.in

post-install:
	(cd ${STAGEDIR}${PREFIX}/bin && ${LN} -sf mdump3 mdump	\
		&& ${LN} -sf xmdump3 xmdump)

.include "${.CURDIR}/../../french/aster/bsd.aster.mk"
.include <bsd.port.mk>
