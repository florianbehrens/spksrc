PKG_NAME = node
PKG_VERS = v10.15.3
PKG_EXT = tar.gz
PKG_DIST_NAME = $(PKG_NAME)-$(PKG_VERS).$(PKG_EXT)
PKG_DIST_SITE = https://nodejs.org/dist/v10.15.3
PKG_DIR = $(PKG_NAME)-$(PKG_VERS)

HOMEPAGE = http://www.nodejs.org
COMMENT  = A JavaScript runtime built on Chrome's V8 JavaScript engine.
LICENSE  = https://github.com/nodejs/node/raw/master/LICENSE

ifeq ($(findstring $(ARCH),$(ARM5_ARCHES)),$(ARCH))
CONFIGURE_ARGS = --arch=arm
endif

ifeq ($(findstring $(ARCH),$(ARM7_ARCHES)),$(ARCH))
CONFIGURE_ARGS = --arch=arm
endif

ifeq ($(findstring $(ARCH),$(ARM8_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --arch=arm64
endif

ifeq ($(findstring $(ARCH),$(x86_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --arch=i386
endif

ifeq ($(findstring $(ARCH),$(x64_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --arch=x86_64
endif

ifeq ($(findstring $(ARCH),$(PPC_ARCHES)),$(ARCH))
CONFIGURE_ARGS += --arch=ppc
endif

CONFIGURE_ARGS += --cross-compiling --dest-os=linux --prefix=$(INSTALL_PREFIX)

ENV += CC_host="gcc -m32"
ENV += CXX_host="g++ -m32"

include ../../mk/spksrc.cross-cc.mk
