#
# Copyright (C) 2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=steamcontroller
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/ynsta/steamcontroller.git
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION=dc9f278879f210ee25bcc0836b044dc1a414b5a5
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_SOURCE_VERSION).tar.gz

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Stany MARCEL <stanypub@gmail.com>

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/steamcontroller
	SECTION:=multimedia
	CATEGORY:=Multimedia
	TITLE:=steamcontroller
	URL:=https://github.com/ynsta/steamcontroller
	DEPENDS:=+python-light +python-enum34 +python-libusb1
endef

define Package/steamcontroller/description
standalone steam controller driver
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/usr --root=$(PKG_INSTALL_DIR))
endef

define PyPackage/steamcontroller/install
	$(INSTALL_DIR) $(1)/usr/bin $(1)/etc/udev/rules.d $(1)/usr/include/linux
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/scripts/sc-callbacks.py $(1)/usr/bin
	$(INSTALL_CONF) ./files/99-steamcontroller.rules $(1)/etc/udev/rules.d/
	$(CP) $(TOOLCHAIN_DIR)/include/linux/input.h $(1)/usr/include/linux/
endef

$(eval $(call PyPackage,steamcontroller))
$(eval $(call BuildPackage,steamcontroller))
