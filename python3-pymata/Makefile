#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-pymata
PKG_VERSION:=2.15
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/MrYsLab/pymata-aio.git
PKG_SOURCE_VERSION:=f1d02654c44bcc2b6619e3597fd18525fef72681

PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_LICENSE:=GPL-3
PKG_LICENSE_FILES:=license.txt

PKG_BUILD_DEPENDS:=+python3-setuptools

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python3-package.mk)

define Package/python3-pymata
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	TITLE:=python3-pymata
	URL:=https://github.com/MrYsLab/pymata-aio/
	DEPENDS:=+python3-asyncio +python3-websockets
	MAINTAINER:=Alan Yorinks <MisterYsLab@gmail.com>
endef

define Package/python3-pymata/description
	A high performance, non-blocking, Python asyncio client for the Firmata Protocol.
endef

define Build/Compile
	$(call Build/Compile/Py3Mod,,\
		install --prefix="/usr" --root="$(PKG_INSTALL_DIR)" \
		--single-version-externally-managed \
	)
endef

$(eval $(call Py3Package,python3-pymata))
$(eval $(call BuildPackage,python3-pymata))
