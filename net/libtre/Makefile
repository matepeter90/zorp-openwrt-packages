include $(TOPDIR)/rules.mk

# Name and release number of this package
PKG_NAME:=libtre
PKG_VERSION:=0.8.0
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)/tre-$(PKG_VERSION)


PKG_SOURCE:=tre_$(PKG_VERSION).orig.tar.gz
PKG_SOURCE_URL:=http://archive.ubuntu.com/ubuntu/pool/universe/t/tre

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/libtre
	CATEGORY:=Libraries
	TITLE:=libtre
endef

#define Build/Configure
#	(cd $(PKG_BUILD_DIR); ./autogen.sh)
#	$(call Build/Configure/Default)
#endef

#define Build/Configure
#	(cd $(PKG_BUILD_DIR); touch NEWS README AUTHORS ChangeLog)
#	(cd $(PKG_BUILD_DIR); autoreconf --force --install; autoconf)
#	$(call Build/Configure/Default);
#endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr
	$(CP) $(PKG_INSTALL_DIR)/usr/* $(1)/usr/
endef

define Package/libtre/install
	$(INSTALL_DIR) $(1)/usr
	$(CP) $(PKG_INSTALL_DIR)/usr/* $(1)/usr/
endef

$(eval $(call BuildPackage,libtre))
