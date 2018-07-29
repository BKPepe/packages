#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyload
PKG_VERSION:=0.4.9
PKG_REV:=bbb3c9c367ae389990e37e68eabf1420362efbec
PKG_RELEASE:=2
PKG_MAINTAINER:=Josef Schlehofer <pepe.schlehofer@gmail.com>
PKG_LICENSE:=GPL-3.0

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/pyload/pyload.git

PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION)-$(PKG_REV).tar.gz

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)/

include $(INCLUDE_DIR)/package.mk

define Package/pyload
  TITLE:=A fast, lightweight and full featured download manager
  URL:=https://pyload.net
  SECTION:=net
  CATEGORY:=Network
  DEPENDS:=  \
    +python +python-openssl +python-curl +python-crypto \
    +python-imaging-library +python-sqlite3 +js \
    +tesseract +unrar
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/pyload/install
	$(INSTALL_DIR) $(1)/usr/share/python
	$(CP) $(PKG_BUILD_DIR)/pyload $(1)/usr/share/python/
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/pyload.init $(1)/etc/init.d/pyload
	$(INSTALL_DIR) $(1)/usr/bin
	$(LN) ../share/python/pyload/pyLoadCore.py $(1)/usr/bin/pyload
endef

$(eval $(call BuildPackage,pyload))
