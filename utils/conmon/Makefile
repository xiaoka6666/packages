include $(TOPDIR)/rules.mk

PKG_NAME:=conmon
PKG_VERSION:=2.1.5
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/containers/$(PKG_NAME)/archive/v$(PKG_VERSION)
PKG_HASH:=ee3179ee2b9a9107acec00eb546062cf7deb847f135a3b81503d22b0d226b3ed

PKG_MAINTAINER:=Oskari Rauta <oskari.rauta@gmail.com>
PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=libseccomp

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk
include $(INCLUDE_DIR)/meson.mk

define Package/conmon
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Podman conmon
  URL:=https://podman.io
  DEPENDS:=@!arc +glib2 $(INTL_DEPENDS) $(ICONV_DEPENDS)
endef

define Package/conmon/description
  An OCI container runtime monitor.

  Conmon is a monitoring program and communication tool between
  a container manager (like Podman or CRI-O) and an OCI runtime
  (like runc or crun) for a single container.
endef

define Package/conmon/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/libexec/podman/conmon $(1)/usr/bin
endef

$(eval $(call BuildPackage,conmon))
