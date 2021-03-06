#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-websockets
PKG_VERSION:=3.1
PKG_RELEASE:=1

PKG_SOURCE:=websockets-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/w/websockets/
PKG_MD5SUM:=71805b52e8586d01fa217092237aeae7

PKG_LICENSE:=BSD
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DIR:=$(BUILD_DIR)/python3-websockets-$(PKG_VERSION)
PKG_UNPACK:=tar -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

PKG_BUILD_DEPENDS:=+python3-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-websockets
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=python3-websockets
	URL:=https://pypi.python.org/pypi/websockets/
	DEPENDS:=+python3-asyncio
	MAINTAINER:=Aymeric Augustin
endef

define Package/python3-websockets/description
	A library for developing WebSocket servers and clients in Python.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
		--single-version-externally-managed \
	)
endef

$(eval $(call Py3Package,python3-websockets))
$(eval $(call BuildPackage,python3-websockets))
