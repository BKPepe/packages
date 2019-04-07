#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pynacl
PKG_VERSION:=1.3.0
PKG_RELEASE:=1

PKG_SOURCE:=PyNaCl-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://files.pythonhosted.org/packages/source/p/pynacl/
PKG_HASH:=0c6100edd16fefd1557da078c7a31e7b7d7a52ce39fdca2bec29d4f7b6e7600c
PKG_BUILD_DIR:=$(BUILD_DIR)/$(BUILD_VARIANT)-pynacl-$(PKG_VERSION)

PKG_MAINTAINER:=Josef Schlehofer <pepe.schlehofer@gmail.com>
PKG_LICENSE:=Apache-2.0
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include ../python-package.mk
include ../python3-package.mk

PKG_UNPACK:=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

define Package/python-pynacl/Default
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Python binding to the libsodium library
  URL:=https://github.com/pyca/pynacl/
  DEPENDS:=+libsodium
endef

define Package/python-pynacl
$(call Package/python-pynacl/Default)
  DEPENDS+= \
    +PACKAGE_python-pynacl:python-light \
    +PACKAGE_python-pynacl:python-six \
    +PACKAGE_python-pynacl:python-cffi \
    +PACKAGE_python-pynacl:python-pycparser
  VARIANT:=python
endef

define Package/python3-pynacl
$(call Package/python-pynacl/Default)
  DEPENDS+= \
    +PACKAGE_python3-pynacl:python3-light \
    +PACKAGE_python3-pynacl:python3-six \
    +PACKAGE_python3-pynacl:python3-cffi \
    +PACKAGE_python3-pynacl:python3-pycparser
  VARIANT:=python3
endef

define Package/python-pynacl/description
  PyNaCl is a Python binding to libsodium, which is a fork of the Networking and Cryptography library.
  These libraries have a stated goal of improving usability, security and speed.
endef

define Package/python3-pynacl/description
$(call Package/python-pynacl/description)
.
(Variant for Python3)
endef

PYTHON_PKG_SETUP_VARS:= SODIUM_INSTALL=system
PYTHON3_PKG_SETUP_VARS:= SODIUM_INSTALL=system

$(eval $(call PyPackage,python-pynacl))
$(eval $(call BuildPackage,python-pynacl))
$(eval $(call BuildPackage,python-pynacl-src))

$(eval $(call Py3Package,python3-pynacl))
$(eval $(call BuildPackage,python3-pynacl))
$(eval $(call BuildPackage,python3-pynacl-src))
