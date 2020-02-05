#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=ipband
PKG_VERSION:=0.8.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tgz
PKG_SOURCE_URL:=http://ipband.sourceforge.net/
PKG_HASH:=f0a5860647d5364df812f7660d28f1ee8fbd35eb27088ab0cd445963db5806ad

PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_PARALLEL:=1
PKG_BUILD_DEPENDS:=libpcap

include $(INCLUDE_DIR)/package.mk

define Package/ipband
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Bandwidth monitoring application
  URL:=http://ipband.sourceforge.net/
  MAINTAINER:=Aristeu Rozanski <aris@ruivo.org>
  DEPENDS:=+libpcap
endef

define Package/ipband/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_DIR) $(1)/etc/ipband
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ipband $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ipband.sample.conf $(1)/etc/ipband
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/ipband.rc $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,ipband,+libpcap))
