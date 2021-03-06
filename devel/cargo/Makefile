# $OpenBSD: Makefile,v 1.7 2016/11/30 09:01:00 landry Exp $
COMMENT = package manager for Rust language

# lang/rust is being worked on for i386, cargo not ready yet
ONLY_FOR_ARCHS =	amd64

# cargo version
CARGO_VERSION =		0.14.0

# rust-install submodule version in cargo/src/rust-installer
# see https://github.com/rust-lang/cargo/tree/${CARGO_VERSION}/src
RUSTINSTALL_INDEX =	4f994850808a572e2cc8d43f968893c8e942e9bf

# crates.io commit for CARGO_VERSION
# see https://github.com/rust-lang/crates.io-index/commits/master/ca/rg/cargo
CRATESIO_INDEX =	9f8c3a65f70b2a5723e0d9cc0a32d531ea42da67

# cargo version used for bootstrapping
BOOTSTRAP_VERSION =	0.14.0-20161112

# registry index
# see ${WRKDIR}/cargo-home/registry/index/github.com-${REGISTRY_INDEX}
REGISTRY_INDEX =	1ecc6299db9ec823


DISTNAME =	cargo-${CARGO_VERSION}
CATEGORIES =	devel

HOMEPAGE =	https://doc.crates.io/

MAINTAINER =	Sebastien Marie <semarie@online.fr>

# cargo is dual licensed MIT/Apache-2.0
# third-parties (detail below):
#  - MIT
#  - Unlicense/MIT
#  - MIT/Apache-2.0
#
PERMIT_PACKAGE_CDROM = Yes

WANTLIB = c crypto curl m pthread ssh2 ssl z

DIST_SUBDIR =	cargo
MASTER_SITES =	https://github.com/rust-lang/
DISTFILES +=	cargo-${CARGO_VERSION}.tar.gz{cargo/archive/${CARGO_VERSION}.tar.gz}
DISTFILES +=	rust-installer-${RUSTINSTALL_INDEX}.tar.gz{rust-installer/archive/${RUSTINSTALL_INDEX}.tar.gz}
DISTFILES +=	crates.io-index-${CRATESIO_INDEX}.tar.gz{crates.io-index/archive/${CRATESIO_INDEX}.tar.gz}

# look at ${WRKDIR}/cargo-home/registry/src/github.com-${REGISTRY_INDEX}
# for the list
CRATES +=	advapi32-sys-0.2.0		# MIT
CRATES +=	aho-corasick-0.5.3		# Unlicense/MIT
CRATES +=	bitflags-0.1.1			# MIT/Apache-2.0
CRATES +=	bitflags-0.7.0			# MIT/Apache-2.0
CRATES +=	bufstream-0.1.2			# MIT/Apache-2.0 (test)
CRATES +=	cfg-if-0.1.0			# MIT/Apache-2.0
CRATES +=	cmake-0.1.17			# MIT/Apache-2.0
CRATES +=	crossbeam-0.2.9			# MIT/Apache-2.0
CRATES +=	curl-0.3.9			# MIT
CRATES +=	curl-sys-0.2.4			# MIT
CRATES +=	docopt-0.6.82			# Unlicense/MIT
CRATES +=	env_logger-0.3.4		# MIT/Apache-2.0
CRATES +=	filetime-0.1.10			# MIT/Apache-2.0
CRATES +=	flate2-0.2.14			# MIT/Apache-2.0
CRATES +=	fs2-0.2.5			# MIT/Apache-2.0
CRATES +=	gcc-0.3.35			# MIT/Apache-2.0
CRATES +=	git2-0.4.4			# MIT/Apache-2.0
CRATES +=	git2-curl-0.5.0			# MIT/Apache-2.0
CRATES +=	glob-0.2.11			# MIT/Apache-2.0
CRATES +=	hamcrest-0.1.1			# MIT/Apache-2.0 (test)
CRATES +=	idna-0.1.0			# MIT/Apache-2.0
CRATES +=	kernel32-sys-0.2.2		# MIT
CRATES +=	lazy_static-0.2.1		# MIT
CRATES +=	libc-0.2.17			# MIT/Apache-2.0
CRATES +=	libgit2-sys-0.4.5		# MIT/Apache-2.0
CRATES +=	libssh2-sys-0.1.39		# MIT/Apache-2.0
CRATES +=	libz-sys-1.0.6			# MIT/Apache-2.0
CRATES +=	log-0.3.6			# MIT/Apache-2.0
CRATES +=	matches-0.1.2			# MIT
CRATES +=	memchr-0.1.11			# Unlicense/MIT
CRATES +=	miniz-sys-0.1.7			# MIT/Apache-2.0
CRATES +=	miow-0.1.3			# MIT/Apache-2.0
CRATES +=	net2-0.2.26			# MIT/Apache-2.0
CRATES +=	num-0.1.36			# MIT/Apache-2.0 (test)
CRATES +=	num-bigint-0.1.35		# MIT/Apache-2.0 (test)
CRATES +=	num-complex-0.1.35		# MIT/Apache-2.0 (test)
CRATES +=	num-integer-0.1.32		# MIT/Apache-2.0 (test)
CRATES +=	num-iter-0.1.32			# MIT/Apache-2.0 (test)
CRATES +=	num-rational-0.1.35		# MIT/Apache-2.0 (test)
CRATES +=	num-traits-0.1.36		# MIT/Apache-2.0 (test)
CRATES +=	num_cpus-1.0.0			# MIT
CRATES +=	openssl-0.7.14			# Apache-2.0
CRATES +=	openssl-sys-0.7.14		# MIT
CRATES +=	openssl-sys-extras-0.7.14	# MIT
CRATES +=	pkg-config-0.3.8		# MIT/Apache-2.0
CRATES +=	psapi-sys-0.1.0			# MIT
CRATES +=	rand-0.3.14			# MIT/Apache-2.0
CRATES +=	regex-0.1.77			# MIT/Apache-2.0
CRATES +=	regex-syntax-0.3.5		# MIT/Apache-2.0
CRATES +=	rustc-serialize-0.3.19		# MIT/Apache-2.0
CRATES +=	semver-0.5.1			# MIT/Apache-2.0
CRATES +=	semver-parser-0.6.1		# MIT/Apache-2.0
CRATES +=	strsim-0.3.0			# MIT
CRATES +=	tar-0.4.8			# MIT/Apache-2.0
CRATES +=	tempdir-0.3.5			# MIT/Apache-2.0
CRATES +=	term-0.4.4			# MIT/Apache-2.0
CRATES +=	thread-id-2.0.0			# Apache-2.0
CRATES +=	thread_local-0.2.6		# Apache-2.0/MIT
CRATES +=	toml-0.2.0			# MIT/Apache-2.0
CRATES +=	unicode-bidi-0.2.3		# MIT/Apache-2.0
CRATES +=	unicode-normalization-0.1.2	# MIT/Apache-2.0
CRATES +=	url-1.2.0			# MIT/Apache-2.0
CRATES +=	utf8-ranges-0.1.3		# Unlicense/MIT
CRATES +=	winapi-0.2.8			# MIT
CRATES +=	winapi-build-0.1.1		# MIT
CRATES +=	ws2_32-sys-0.2.1		# MIT

MASTER_SITES0 =	https://crates.io/api/v1/crates/
.for _crate in ${CRATES}
DISTFILES +=	${_crate}.tar.gz{${_crate:C/-[^-]*$//}/${_crate:C/^.*-//}/download}:0
.endfor

MASTER_SITES1 = http://kapouay.odns.fr/pub/cargo/
DISTFILES +=	cargo-bootstrap-${BOOTSTRAP_VERSION}.tar.gz:1

MODULES =	lang/python
MODPY_RUNDEP =	No

USE_GMAKE =	Yes

BUILD_DEPENDS =	devel/libgit2/libgit2 \
		devel/cmake \
		lang/rust>=1.13,<1.14

LIB_DEPENDS =	net/curl \
		security/libssh2

RUN_DEPENDS =	lang/rust

CONFIGURE_STYLE =	simple
CONFIGURE_ARGS +=	--prefix=${LOCALBASE} \
			--mandir=${LOCALBASE}/man \
			--local-rust-root=${LOCALBASE} \
			--local-cargo=${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_VERSION}/cargo

MAKE_ENV +=	CARGO_HOME=${WRKDIR}/cargo-home \
		VERBOSE=1 \
		LIBSSH2_SYS_USE_PKG_CONFIG=1

post-extract:
	# place rust-installer inside WRKSRC
	rmdir ${WRKSRC}/src/rust-installer
	mv ${WRKDIR}/rust-installer-${RUSTINSTALL_INDEX} \
		${WRKSRC}/src/rust-installer
	# populate cargo registry to avoid downloading crates
	mkdir -p ${WRKDIR}/cargo-home/registry/{cache,index,src}
	mkdir ${WRKDIR}/cargo-home/registry/{cache,src}/github.com-${REGISTRY_INDEX}
	mv ${WRKDIR}/crates.io-index-${CRATESIO_INDEX} \
		${WRKDIR}/cargo-home/registry/index/github.com-${REGISTRY_INDEX}
	touch ${WRKDIR}/cargo-home/registry/index/github.com-${REGISTRY_INDEX}/.cargo-index-lock
.for _crate in ${CRATES}
	gzip < /dev/null \
		> ${WRKDIR}/cargo-home/registry/cache/github.com-${REGISTRY_INDEX}/${_crate}.crate
	mv ${WRKDIR}/${_crate} \
		${WRKDIR}/cargo-home/registry/src/github.com-${REGISTRY_INDEX}
	touch ${WRKDIR}/cargo-home/registry/src/github.com-${REGISTRY_INDEX}/${_crate}/.cargo-ok
.endfor

SUBST_VARS +=	WRKBUILD
pre-test:
	${SUBST_CMD} ${WRKSRC}/tests/cargotest/support/paths.rs

post-install:
	rm -rf ${PREFIX}/lib/rustlib
	mkdir -p ${PREFIX}/share/bash-completion/completions
	mv ${PREFIX}${SYSCONFDIR}/bash_completion.d/cargo \
	       ${PREFIX}/share/bash-completion/completions
	rmdir ${PREFIX}${SYSCONFDIR}/bash_completion.d \
		${PREFIX}${SYSCONFDIR}

# make a directory suitable for bootstrapping
BOOTSTRAP_NVERSION = ${CARGO_VERSION}-new
bootstrap: fake
	rm -rf ${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_NVERSION}
	mkdir -p ${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_NVERSION}
	cp ${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_VERSION}/cargo \
		${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_NVERSION}/cargo
	cp ${WRKINST}${PREFIX}/bin/cargo \
		${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_NVERSION}/cargo.bin
	ldd ${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_NVERSION}/cargo.bin \
		| sed -ne 's,.* \(/.*/lib/lib.*\.so[.0-9]*\)$$,\1,p' \
		| xargs -r -J % cp % \
			${WRKDIR}/cargo-bootstrap-${BOOTSTRAP_NVERSION}

.include <bsd.port.mk>
