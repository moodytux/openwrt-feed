# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=chkrootkit
PKG_VERSION:=0.52
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=ftp://ftp.pangeia.com.br/pub/seg/pac/
PKG_HASH:=c578c0b9c8ae0729c2de7075f896f3d168e768c52e319a7706c9a7e46ff7a211

PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk

define Package/chkrootkit
  SECTION:=admin
  CATEGORY:=Administration
  TITLE:=chkrootkit
  DEPENDS:=
  URL:=http://www.chkrootkit.org/
endef

define Package/chkrootkit/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/chkrootkit $(1)/usr/sbin/chkrootkit
endef

$(eval $(call BuildPackage,chkrootkit))
