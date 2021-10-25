#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python3-docx
PKG_VERSION:=0.8.11
PKG_RELEASE:=1

PYPI_NAME:=python-docx
PKG_HASH:=1105d233a0956dd8dd1e710d20b159e2d72ac3c301041b95f4d4ceb3e0ebebc4

include $(TOPDIR)/feeds/packages/lang/python/pypi.mk
include $(INCLUDE_DIR)/package.mk
include $(TOPDIR)/feeds/packages/lang/python/python3-package.mk

define Package/python3-docx
  SUBMENU:=Python
  SECTION:=lang
  CATEGORY:=Languages
  TITLE:= python-docx is a Python library for creating and updating Microsoft Word (.docx) files.
  URL:=https://github.com/python-openxml/python-docx
  DEPENDS:= \
	  +python3-light \
	  +python3-lxml
endef

define Package/python3-docx/description
  python-docx is a Python library for creating and updating Microsoft Word (.docx) files.
endef

$(eval $(call Py3Package,python3-docx))
$(eval $(call BuildPackage,python3-docx))
$(eval $(call BuildPackage,python3-docx-src))
