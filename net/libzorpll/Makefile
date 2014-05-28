include $(TOPDIR)/rules.mk

# Name and release number of this package
PKG_NAME:=libzorpll
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

PKG_VERSION:=5.0.0.0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/balabit/libzorpll.git
PKG_SOURCE_SUBDIR:=libzorpll
PKG_SOURCE_VERSION:=52234466db9f685d1631fa93a6d81dbd0011ca88
PKG_SOURCE_PROTO:=git

PKG_INSTALL:=1
PKG_BUILD_DEPENDS:= +libopenssl +libiconv-full +libstdcpp

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/libzorpll
	CATEGORY:=Libraries
	TITLE:=libzorpll
    DEPENDS:= +glib2 +libopenssl +zlib +libstdcpp
endef

define Build/Configure
	(cd $(PKG_BUILD_DIR); ./autogen.sh)
	$(call Build/Configure/Default)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr
	$(CP) $(PKG_INSTALL_DIR)/usr/* $(1)/usr/
endef

define Package/libzorpll/install
	$(INSTALL_DIR) $(1)/usr
	$(CP) $(PKG_INSTALL_DIR)/usr/* $(1)/usr/
endef

$(eval $(call BuildPackage,libzorpll,+glib2,+libopenssl,+zlib,+libstdcpp))
