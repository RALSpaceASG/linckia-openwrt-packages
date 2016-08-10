#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-json-rpc
PKG_VERSION:=1.10.3
PKG_RELEASE:=1

PKG_SOURCE:=json-rpc-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/j/json-rpc/
PKG_MD5SUM:=24e9765de545ed2df6f06e229c88a9c8

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE.txt

PKG_BUILD_DIR:=$(BUILD_DIR)/python3-json-rpc-$(PKG_VERSION)
PKG_UNPACK:=tar -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

PKG_BUILD_DEPENDS:=+python3-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-json-rpc
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=python3-json-rpc
	URL:=https://pypi.python.org/pypi/json-rpc/
	DEPENDS:=+python3-asyncio
	MAINTAINER:=Kirill Pavlov
endef

define Package/python3-json-rpc/description
	JSON-RPC2.0 and JSON-RPC1.0 transport specification implementation.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
		--single-version-externally-managed \
	)
endef

$(eval $(call Py3Package,python3-json-rpc))
$(eval $(call BuildPackage,python3-json-rpc))
