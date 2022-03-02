# Copyright (C) 2022
#
# This is free software, licensed under the GNU General Public License v2.


include $(TOPDIR)/rules.mk

PKG_NAME:=trumeter-utility
PKG_VERSION:=1
PKG_RELEASE=0

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_VERSION:=HEAD
PKG_SOURCE_URL:=https://github.com/overmyerD/trumeter-utility.git
PKG_SOURCE_PROTO:=git

PKG_MAINTAINER:=Dalton Overmyer <dalton@raptorpowersystems.com>
PKG_LICENSE:=GPL-2.0+

include $(INCLUDE_DIR)/package.mk
include $(INCLUDE_DIR)/cmake.mk

define Package/trumeter-utility
  SECTION:=rator
  CATEGORY:=Raptor
  SUBMENU:=Utilities
  TITLE:=A simple utility that reads the values of a Trumeter.
  DEPENDS:=+libubox +libubus
endef

TARGET_CFLAGS += -I$(STAGING_DIR)/usr/include


define Package/trumeter-utility/install
	$(INSTALL_DIR) $(1)/usr/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/trumeter-utility $(1)/usr/sbin/
endef

$(eval $(call BuildPackage,trumeter-utility))