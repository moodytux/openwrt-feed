# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=aide
PKG_VERSION:=0.16
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=@SF/$(PKG_NAME)
PKG_HASH:=a81c53a131c4fd130b169b3a26ac35386a2f6e1e014f12807524cc273ed97345
PKG_LICENSE:=GPL-2.0-only
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/aide
	SECTION:=admin
	CATEGORY:=Administration
	DEPENDS:=+libgcrypt
	TITLE:=AIDE
	URL:=http://aide.sourceforge.net/
endef

define Package/aide/description
	This package contains aide and associated utilities.
endef

define Build/Configure
	$(call Build/Configure/Default)
	sed -i 's/D\["AIDE_INO_TYPE"\]=.*/D\["AIDE_INO_TYPE"\]=" ino_t"/' $(PKG_BUILD_DIR)/config.status
endef

define Package/aide/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/aide $(1)/usr/sbin/aide
	$(INSTALL_DIR) $(1)/etc/aide
	$(INSTALL_BIN) ./files/aide.conf $(1)/etc/aide/aide.conf
endef

$(eval $(call BuildPackage,aide))
