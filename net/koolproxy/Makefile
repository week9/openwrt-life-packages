#
# Copyright (C) 2015-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v3.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=koolproxy
PKG_VERSION:=3.8.4
PKG_RELEASE:=1

ifeq ($(ARCH),i386)
	PKG_ARCH_koolproxy:=386
endif
ifeq ($(ARCH),x86_64)
	PKG_ARCH_koolproxy:=amd64
endif
ifeq ($(ARCH),arm)
	PKG_ARCH_koolproxy:=arm
endif
ifeq ($(ARCH),mips)
	PKG_ARCH_koolproxy:=mips
endif
ifeq ($(ARCH),mipsel)
	PKG_ARCH_koolproxy:=mipsel
endif

include $(INCLUDE_DIR)/package.mk

define Package/$(PKG_NAME)
	SECTION:=net
	CATEGORY:=Network
	TITLE:=KoolProxy
	DEPENDS:=@(i386||x86_64||arm||mipsel||mips)
	URL:=https://github.com/user1121114685/koolproxyR
endef

define Package/$(PKG_NAME)/description
	This package for koolproxy.
endef

define Build/Prepare
endef

define Build/Configure
endef

define Build/Compile
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)/usr/share/koolproxy
	$(INSTALL_BIN) ./files/$(PKG_ARCH_koolproxy)/koolproxy $(1)/usr/share/koolproxy/koolproxy
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
