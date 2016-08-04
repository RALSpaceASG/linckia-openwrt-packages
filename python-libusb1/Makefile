#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-libusb1
PKG_VERSION:=1.4.1
PKG_RELEASE:=1

PKG_SOURCE:=libusb1-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://pypi.python.org/packages/source/l/libusb1
PKG_MD5SUM:=19c51395c4b2e1d0357000c6018cf65b

PKG_LICENSE:=LGPL-2.1+
PKG_LICENSE_FILES:=COPYING
PKG_MAINTAINER:=Vincent Pelletier <plr.vincent@gmail.com>

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-libusb1
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=python-libusb1
	URL:=https://pypi.python.org/pypi/libusb1/
	DEPENDS:=+python-light
endef

define Package/python-libusb1/description
pure-python wrapper for libusb-1.0
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

$(eval $(call PyPackage,python-libusb1))
$(eval $(call BuildPackage,python-libusb1))
