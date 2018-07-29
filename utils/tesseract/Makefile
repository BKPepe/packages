#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=tesseract
PKG_VERSION:=3.05.02
PKG_RELEASE:=1
PKG_MAINTAINER:=Josef Schlehofer <pepe.schlehofer@gmail.com>
PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=COPYING

PKG_SOURCE_URL:=https://codeload.github.com/tesseract-ocr/tesseract/tar.gz/$(PKG_VERSION)?
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
#PKG_HASH:=494d64ffa7069498a97b909a0e65a35a213989e0184f1ea15332933a90d43445
PKG_MD5SUM:=d3b8661f878aed931cf3a7595e69b989


PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)

PKG_FIXUP:=autoreconf
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/tesseract
  SECTION:=utils
  CATEGORY:=Utilities
  TITLE:=Tesseract Open Source OCR Engine
  URL:=https://github.com/tesseract-ocr/tesseract
  DEPENDS:=+libleptonica +libpthread +libstdcpp
endef

CONFIGURE_ARGS += \
	LIBLEPT_HEADERSDIR="$(STAGING_DIR)/usr/include" \

TARGET_LDFLAGS += -Wl,-rpath-link=$(STAGING_DIR)/usr/lib

define Build/Prepare
	$(call Build/Prepare/Default)
	$(SED) '1s/^\xEF\xBB\xBF//' $(PKG_BUILD_DIR)/ccutil/strngs.h
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/include
	$(CP) $(PKG_INSTALL_DIR)/usr/include/tesseract $(1)/usr/include/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libtesseract.{a,so*} $(1)/usr/lib/
endef

define Package/tesseract/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/lib*.so.* $(1)/usr/lib/
	$(INSTALL_DIR) $(1)/usr/share
	$(CP) $(PKG_INSTALL_DIR)/usr/share/* $(1)/usr/share/
endef

$(eval $(call BuildPackage,tesseract))