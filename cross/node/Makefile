PKG_NAME = node
PKG_VERS = v10.15.3
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://nodejs.org/dist/v10.15.3
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

REQUIRED_DSM = 6.1
UNSUPPORTED_ARCHS = 88f6281 aarch64 armada37xx qoriq rtd1296

HOMEPAGE = http://www.nodejs.org
COMMENT  = A JavaScript runtime built on Chrome\'s V8 JavaScript engine.
LICENSE  = https://github.com/nodejs/node/raw/master/LICENSE

ENV += CC_host="gcc -m32"
ENV += CXX_host="g++ -m32"

CONFIGURE_ARGS = --cross-compiling --dest-os=linux --prefix=$(INSTALL_PREFIX)

include ../../mk/spksrc.cross-cc.mk

ifeq ($(findstring $(ARCH),$(ARM5_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --dest-cpu=arm
endif

ifeq ($(findstring $(ARCH),$(ARM7_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --dest-cpu=arm
endif

ifeq ($(findstring $(ARCH),$(ARM8_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --dest-cpu=arm64
endif

ifeq ($(findstring $(ARCH),$(x86_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --dest-cpu=x86
endif

ifeq ($(findstring $(ARCH),$(x64_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --dest-cpu=x86_64 --openssl-no-asm
endif

ifeq ($(findstring $(ARCH),$(PPC_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --dest-cpu=ppc
endif

