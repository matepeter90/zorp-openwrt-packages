include $(TOPDIR)/rules.mk

# Name and release number of this package
PKG_NAME:=zorp
PKG_VERSION:=5.0.0
PKG_BUILD_DIR := $(BUILD_DIR)/$(PKG_NAME)

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://github.com/balabit/zorp.git
PKG_SOURCE_SUBDIR:=zorp
PKG_SOURCE_VERSION:=2af6ad1035fc8b7307072d081a6da263ae0e91bc
PKG_SOURCE_PROTO:=git

#PKG_LICENSE:=LGPLv2.1 GPLv2

PKG_INSTALL:=1

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/include/zorp -std=c99 -fPIC
TARGET_LDFLAGS += -L$(STAGING_DIR)/usr/lib -pthread -lz

PKG_BUILD_DEPENDS:= +python +glib2 +libopenssl +libpthread +libzorpll +libtre +kmod-kzorp +zorp-addons +kzorp-addons +python-radix +pyopenssl +pydns +iptables-mod-tproxy +iptables-mod-ipopt +iptables-mod-conntrack-extra

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/nls.mk

define Package/zorp
	CATEGORY:=Network
	TITLE:=zorp
	DEPENDS:= +python +glib2 +libopenssl +libpthread +libzorpll +libtre +kmod-kzorp +zorp-addons +kzorp-addons +python-radix +pyopenssl +pydns +iptables-mod-tproxy +iptables-mod-ipopt +iptables-mod-conntrack-extra
endef

define Build/Configure
	(cd $(PKG_BUILD_DIR); ./autogen.sh)
	$(call Build/Configure/Default,--with-pidfiledir=/var/run)
endef

define Build/Compile
	sed -i 's/\-\-install\-layout\=deb//g' $(PKG_BUILD_DIR)/pylib/kzorp/Makefile.am;
endef


define Package/zorp/install
	$(INSTALL_DIR) $(1)/etc
	$(INSTALL_DIR) $(1)/usr
	$(INSTALL_DIR) $(1)/etc/iproute2
	touch $(1)/etc/iproute2/group
	$(CP) $(PKG_INSTALL_DIR)/usr/* $(1)/usr/
	$(CP) $(PKG_INSTALL_DIR)/etc/* $(1)/etc/
endef

$(eval $(call BuildPackage,zorp,+python,+glib2,+libopenssl,+libzorpll,+libpthread,+libtre,+kmod-kzorp,+kzorp-addons,+zorp-addons,+python-radix,+pyopenssl,+pydns,+iptables-mod-tproxy,+iptables-mod-ipopt,+iptables-mod-conntrack-extra))
