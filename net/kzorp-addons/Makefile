include $(TOPDIR)/rules.mk

# Name and release number of this package
PKG_NAME:=kzorp-addons
PKG_RELEASE:=1
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/kzorp-addons
	SECTION:=utils
	CATEGORY:=Utilities
	TITLE:=Kzorp addons
	DEPENDS:= +libxtables
endef

define Build/Prepare
	mkdir -p $(PKG_BUILD_DIR)
	$(CP) ./src/* $(PKG_BUILD_DIR)/
endef

define Package/kzorp-addons/install
	$(INSTALL_DIR) $(1)/usr/lib/iptables
	$(CP) $(PKG_BUILD_DIR)/libxt_KZORP.so $(1)/usr/lib/iptables
endef

$(eval $(call BuildPackage,kzorp-addons,+libxtables))
