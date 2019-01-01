#
# Copyright (C) 2017 Chris Blake (chrisrblake93@gmail.com)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=beep
PKG_VERSION:=1.3
PKG_REV:=f8c6cbbceb3776aa64397cdf856e50f3bc4d8332
PKG_RELEASE:=2

PKG_SOURCE_URL:=https://github.com/ndim/beep.git
PKG_SOURCE_PROTO:=git

PKG_SOURCE_VERSION:=$(PKG_REV)
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)

PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

include $(INCLUDE_DIR)/package.mk

define Package/beep
  SECTION:=sound
  CATEGORY:=Sound
  DEPENDS:=@(TARGET_x86||TARGET_x86_64) +kmod-pcspkr
  TITLE:=Play beep sounds through a PC speaker
  URL:=http://johnath.com/beep/
endef

define Package/beep/description
	Plays beeps through the PC speaker
endef

MAKE_FLAGS += \
	CFLAGS="$(TARGET_CFLAGS)"

define Package/beep/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/beep $(1)/usr/bin
endef

$(eval $(call BuildPackage,beep))
