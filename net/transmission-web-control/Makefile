include $(TOPDIR)/rules.mk

PKG_NAME:=transmission-web-control
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/ronggang/transmission-web-control
PKG_SOURCE_DATE:=2020-02-24
PKG_SOURCE_VERSION:=91ea7ab968d5f1e044b2ee3e062c54384de43cd3

PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE
PKG_MAINTAINER:=Richard Yu <yurichard3839@gmail.com>

include $(INCLUDE_DIR)/package.mk

define Package/transmission-web-control
  SECTION:=net
  CATEGORY:=Network
  SUBMENU:=BitTorrent
  DEPENDS:=+transmission-daemon-openssl
  CONFLICTS:=transmission-web
  TITLE:=Transmission Web Control
  URL:=https://github.com/ronggang/transmission-web-control
  PKGARCH:=all
endef

define Package/transmission-web-control/description
 Transmission Web Control is a custom Web UI for Transmission.
endef

define Build/Compile
endef

define Package/transmission-web-control/install
	$(INSTALL_DIR) $(1)/usr/share/transmission/web
	$(CP) $(PKG_BUILD_DIR)/src/* $(1)/usr/share/transmission/web
endef

$(eval $(call BuildPackage,transmission-web-control))
