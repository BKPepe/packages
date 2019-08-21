#
# Copyright (C) 2019 CZ.NIC, z. s. p. o. (https://www.nic.cz/)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-ruamel-yaml-clib
PKG_VERSION:=0.1.2
PKG_RELEASE:=1

PKG_SOURCE:=ruamel.yaml.clib-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/r/ruamel.yaml.clib/
PKG_HASH:=cee86ecc893a6a8ecaa7c6a9c2d06f75f614176210d78a5f155f8e78d6989509
PKG_BUILD_DIR:=$(BUILD_DIR)/ruamel.yaml.clib-$(PKG_VERSION)

PKG_MAINTAINER:=Josef Schlehofer <josef.schlehofer@nic.cz>
PKG_LICENSE:=BSD-2-Clause
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-ruamel-yaml-clib
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=C version of reader, parser and emitter for ruamel.yaml
  URL:=https://github.com/getsentry/sentry-python
  DEPENDS:=+python3-ruamel-yaml
  VARIANT:=python3
endef

define Package/python3-ruamel-yaml-clib/description
  Python Sentry-Python is an SDK for Sentry.
endef

$(eval $(call Py3Package,python3-ruamel-yaml-clib))
$(eval $(call BuildPackage,python3-ruamel-yaml-clib))
$(eval $(call BuildPackage,python3-ruamel-yaml-clib-src))
