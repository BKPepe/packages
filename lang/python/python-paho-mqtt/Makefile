# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-paho-mqtt
PKG_VERSION:=1.4.0
PKG_RELEASE:=1

PKG_SOURCE:=paho-mqtt-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/paho-mqtt
PKG_HASH:=e440a052b46d222e184be3be38676378722072fcd4dfd2c8f509fb861a7b0b79

PKG_BUILD_DIR:=$(BUILD_DIR)/paho-mqtt-$(PKG_VERSION)

PKG_LICENSE:=Eclipse Public License v1.0 / Eclipse Distribution License v1.0
PKG_LICENSE_FILES:=LICENSE.txt
PKG_MAINTAINER:=Josef Schlehofer <josef.schlehofer@nic.cz>, Alexandru Ardelean <ardeleanalex@gmail.com>

include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-paho-mqtt
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=python3-paho-mqtt
  URL:=http://eclipse.org/paho
  DEPENDS:=+python3-light
  VARIANT:=python3
endef

define Package/python3-paho-mqtt/description
  MQTT version 3.1/3.1.1 client class
endef

$(eval $(call Py3Package,python3-paho-mqtt))
$(eval $(call BuildPackage,python3-paho-mqtt))
$(eval $(call BuildPackage,python3-paho-mqtt-src))
