#
# Copyright (C) 2010-2012 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=miniupnpc
PKG_VERSION:=2.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://miniupnp.tuxfamily.org/files
PKG_HASH:=e19fb5e01ea5a707e2a8cb96f537fbd9f3a913d53d804a3265e3aeab3d2064c6

PKG_MAINTAINER:=
PKG_LICENSE:=BSD-3-Clause
PKG_LICENSE_FILES:=LICENSE
PKG_CPE_ID:=cpe:/a:miniupnp_project:miniupnp

CMAKE_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/miniupnpc/Default
  TITLE:=Lightweight UPnP
  URL:=https://miniupnp.tuxfamily.org
endef

define Package/miniupnpc
  $(call Package/miniupnpc/Default)
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=Firewall
  TITLE+= client
  DEPENDS:=+libminiupnpc
endef

define Package/libminiupnpc
  $(call Package/miniupnpc/Default)
  SECTION:=libs
  CATEGORY:=Libraries
  TITLE+= library
endef

CMAKE_OPTIONS += -DUPNPC_BUILD_TESTS=OFF

TARGET_CFLAGS += $(FPIC)
TARGET_LDFLAGS += -Wl,--gc-sections,--as-needed

define Package/miniupnpc/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/upnpc-shared $(1)/usr/bin/upnpc
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/listdevices $(1)/usr/bin/
endef

define Package/libminiupnpc/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) $(PKG_INSTALL_DIR)/usr/lib/libminiupnpc.so.* $(1)/usr/lib/
endef

$(eval $(call BuildPackage,miniupnpc))
$(eval $(call BuildPackage,libminiupnpc))
