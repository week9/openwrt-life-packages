#
# Copyright (C) 2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ariang
PKG_VERSION:=1.1.6
PKG_RELEASE:=1

include $(INCLUDE_DIR)/package.mk

define Package/ariang
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Download Manager
  DEPENDS:=+uhttpd +aria2
  TITLE:=AriaNg is a web frontend making aria2 easier to use.
  URL:=https://github.com/mayswind/ariaNg
  PKGARCH:=all
endef

define Package/ariang/description
	AriaNg is a web frontend making aria2 easier to use. AriaNg is written in pure html & javascript, thus it does not need any compilers or runtime environment.
endef

define Build/Compile
endef

define Package/ariang/install
	$(INSTALL_DIR) $(1)/www/ariang
	$(CP) ./files/* $(1)/www/ariang
endef

$(eval $(call BuildPackage,ariang))
