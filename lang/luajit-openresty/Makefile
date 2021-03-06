# Created by: Martin Matuska <mm@FreeBSD.org>
# $FreeBSD$

PORTNAME=	luajit
DISTVERSIONPREFIX=	v
DISTVERSION=	2.1-20200102
CATEGORIES=	lang
PKGNAMESUFFIX=	-openresty

PATCH_SITES=	https://github.com/openresty/luajit2/commit/
PATCHFILES=	981ec8d2aac5cac76bdedd4015b6d32447b29597.patch:-p1 \
		2763a421d6219c8cb2bbd39246de619dc796bab6.patch:-p1

MAINTAINER=	mm@FreeBSD.org
COMMENT=	Just-In-Time Compiler for Lua (OpenResty branch)

LICENSE=	MIT PD
LICENSE_COMB=	multi
LICENSE_FILE=	${WRKSRC}/COPYRIGHT

USES=		gmake

CONFLICTS_INSTALL=	luajit

USE_LDCONFIG=	yes
MAKE_ARGS=	CC=${CC}

USE_GITHUB=	yes
GH_ACCOUNT=	openresty
GH_PROJECT=	luajit2

LUAJIT_VERSION=	2.1.0-beta3
LUAJIT_SOVERSION=	2.1.0

PLIST_SUB+=	VERSION=${LUAJIT_VERSION} SOVERSION=${LUAJIT_SOVERSION}

.include <bsd.port.options.mk>

.if ${ARCH:Mpowerpc*} || ${ARCH:Mmips*}
USE_GCC=yes
.endif

post-install:
	${LN} -sf ${PORTNAME}-${LUAJIT_VERSION} \
		${STAGEDIR}${PREFIX}/bin/${PORTNAME}
	${INSTALL_MAN} ${WRKSRC}/etc/luajit.1 ${STAGEDIR}${MAN1PREFIX}/man/man1

.include <bsd.port.mk>
