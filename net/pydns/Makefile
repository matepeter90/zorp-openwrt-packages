#
# Copyright (C) 2009-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pydns
PKG_VERSION:=2.3.6
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://downloads.sourceforge.net/project/pydns/pydns/pydns-2.3.6
PKG_MD5SUM:=d12ca75251854ab6fcabbaff6909b690

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/pydns
	SECTION:=lang-python
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=pydns
	DEPENDS:=+python
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define Package/pydns/description
	pydns
endef

define Package/pydns/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)/
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,pydns))
