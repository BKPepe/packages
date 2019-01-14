#
# Copyright (C) 2019 Josef Schlehofer (pepe.schlehofer@gmail.com)
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=neovim
PKG_VERSION:=0.3.4
PKG_RELEASE:=1

PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/neovim/neovim/tar.gz/v$(PKG_VERSION)?
PKG_HASH:=01b9a4fadb991dd3707ef12ba9ffe1f6d57e119f5d9bb9634e89cd8e130f41bf

PKG_MAINTAINER:=Josef Schlehofer <pepe.schlehofer@gmail.com>
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/neovim
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libncurses
  TITLE:=Vim-fork focused on extensibility and usability
  URL:=https://neovim.io
endef

define Package/neovim/description
	Vim-fork focused on extensibility and usability
endef

define Package/neovim/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_DIR) $(1)/usr/share/neovim
	$(INSTALL_CONF) ./files/vimrc $(1)/usr/share/vim/vimrc
endef

$(eval $(call BuildPackage,neovim))
