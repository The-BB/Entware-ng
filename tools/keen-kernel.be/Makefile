# 
# Copyright (C) 2006-2015 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=keen-kernel.be
PKG_VERSION:=20160729
PKG_REV:=523ac1b7fc214b371973e0d3126cbdb30ef28aec

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_SUBDIR:=$(PKG_NAME)-$(PKG_VERSION)
PKG_SOURCE_URL:=https://github.com/ndmsystems/linux-2.6.22-tc.git
PKG_SOURCE_PROTO:=git
PKG_SOURCE_VERSION:=$(PKG_REV)
HOST_BUILD_DIR:=$(BUILD_DIR_HOST)/linux-2.6.22-tc.be
HOST_UNPACK:=tar -C $(HOST_BUILD_DIR) --strip-components=1 -xf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/host-build.mk

define Host/Compile
endef

define Host/Install
endef

define Host/Clean
	rm -fr $(BUILD_DIR_HOST)/linux-2.6.22-tc.be
endef

$(eval $(call HostBuild))
