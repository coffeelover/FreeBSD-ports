# Created by: Jean-Sébastien Pédron <dumbbell@FreeBSD.org>
# $FreeBSD$

PORTVERSION=	1.48.0.${NIGHTLY_DATE:C,-,,g}
# Always set PORTREVISION explicitly as otherwise it is inherited from lang/rust
PORTREVISION=	0
PKGNAMESUFFIX=	-nightly
DISTNAME=	rustc-nightly-src

ONLY_FOR_ARCHS=	amd64 i386
ONLY_FOR_ARCHS_REASON=	upstream does not provide bootstraps for other architectures

CONFLICTS_INSTALL=	rust

MASTERDIR=	${.CURDIR}/../rust
PATCHDIR=	${.CURDIR}/files
DISTINFO_FILE=	${.CURDIR}/distinfo

OPTIONS_EXCLUDE=	DOCS

# Get latest from top level 'date' key in
# https://static.rust-lang.org/dist/channel-rust-nightly.toml
NIGHTLY_DATE=	2020-09-07

# See WRKSRC/src/stage0.txt for this date
BOOTSTRAPS_DATE=		2020-08-26
RUST_BOOTSTRAP_VERSION=		beta
CARGO_BOOTSTRAP_VERSION=	beta

.include "${MASTERDIR}/Makefile"
