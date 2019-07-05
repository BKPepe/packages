#
# Copyright (C) 2019 CZ.NIC, z. s. p. o. (https://www.nic.cz/)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-qrcodeng
PKG_VERSION:=1.3.3
PKG_RELEASE:=1

PKG_SOURCE:=PyQRCodeNG-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/PyQRCodeNG/
PKG_HASH:=85a8a1e1a4ca8f6beb9579cbda43c084662e904788bc236f3d441490a59a0c15
PKG_BUILD_DIR:=$(BUILD_DIR)/PyQRCodeNG-$(PKG_VERSION)

PKG_MAINTAINER:=Josef Schlehofer <josef.schlehofer@nic.cz>
PKG_LICENSE:=BSD
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python-qrcodeng
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=PyQRCodeNG
  URL:=https://github.com/pyqrcode/pyqrcodeNG
	DEPENDS:=python3-light
	VARIANT:=python3
endef
endef

define Package/python-qrcodeng/description
  The PyQRCodeNG module is a QR code generator that is simple to use and written in pure Python.
  The module can automates most of the building process for creating QR codes. 
  Most codes can be created using only two lines of code!
endef

$(eval $(call Py3Package,python3-qrcodeng))
$(eval $(call BuildPackage,python3-qrcodeng))
$(eval $(call BuildPackage,python3-qrcodeng-src))
