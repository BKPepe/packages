#
# Copyright (C) 2019 CZ.NIC, z. s. p. o. (https://www.nic.cz/)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyqrcode
PKG_VERSION:=1.2.1
PKG_RELEASE:=1

PKG_SOURCE:=PyQRCode-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/P/PyQRCode/
PKG_HASH:=fdbf7634733e56b72e27f9bce46e4550b75a3a2c420414035cae9d9d26b234d5
PKG_BUILD_DIR:=$(BUILD_DIR)/PyQRCode-$(PKG_VERSION)

PKG_MAINTAINER:=Josef Schlehofer <josef.schlehofer@nic.cz>
PKG_LICENSE:=BSD
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/pyqrcode
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=PyQRCode
  URL:=https://github.com/mnooner256/pyqrcode
	DEPENDS:=python3-light
	VARIANT:=python3
endef

define Package/pyqrcode/description
  The PyQRCode module is a QR code generator that is simple to use and written in pure Python.
  The module can automates most of the building process for creating QR codes.
  Most codes can be created using only two lines of code!
endef

$(eval $(call Py3Package,pyqrcode))
$(eval $(call BuildPackage,pyqrcode))
$(eval $(call BuildPackage,pyqrcode))
