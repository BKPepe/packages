#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pyload
PKG_VERSION:=0.4.9
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/pyload/pyload.git
PKG_SOURCE_VERSION=417e60c044bcf90826948bbc15f913696fbf3de2
PKG_MIRROR_HASH:=#todo
	
PKG_MAINTAINER:=Josef Schlehofer <pepe.schlehofer@gmail.com>
PKG_LICENSE:=GPL-3.0
PKG_LICENSE_FILES:=LICENSE.MD

include $(INCLUDE_DIR)/package.mk

define Package/pyload
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Download Manager
  URL:=https://pyload.net
  DEPENDS:= \
    +python3 \
		+python3-openssl \
		+python3-curl \
		+python3-crypto \
    +python3-pillow \ #TO-DO
		+python3-sqlite3 \
    +tesseract
		+unrar
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
