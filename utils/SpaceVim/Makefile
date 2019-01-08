#
# Copyright (C) 2019 Josef Schlehofer (pepe.schlehofer@gmail.com)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=SpaceVim
PKG_VERSION:=1.0.0
PKG_RELEASE:=1

PKG_LICENSE:=GPL-3.0
PKG_LICENSE_FILES:=LICENSE

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/SpaceVim/SpaceVim/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=01b9a4fadb991dd3707ef12ba9ffe1f6d57e119f5d9bb9634e89cd8e130f41bf

PKG_MAINTAINER:=Josef Schlehofer <pepe.schlehofer@gmail.com>
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/SpaceVim
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libncurses +neovim
  TITLE:=A modern community-driven vim editor
  URL:=https://spacevim.org/
endef

define Package/SpaceVim/description
	Modern Vim distribution. SpaceVim manages collections of plugins in layers.
	It is inspirated by spacemacs.
endef

define Package/SpaceVim/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/share/spacevim
	$(INSTALL_CONF) ./files/vimrc $(1)/usr/share/vim/vimrc
endef

$(eval $(call BuildPackage,SpaceVim))
