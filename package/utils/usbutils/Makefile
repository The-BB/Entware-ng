#
# Copyright (C) 2007-2016 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=usbutils
PKG_VERSION:=007
PKG_RELEASE:=6

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=@KERNEL/linux/utils/usb/usbutils
PKG_HASH:=7593a01724bbc0fd9fe48e62bc721ceb61c76654f1d7b231b3c65f6dfbbaefa4
PKG_LICENSE:=GPL-2.0
PKG_LICENSE_FILES:=COPYING

PKG_BUILD_PARALLEL:=1
PKG_INSTALL:=1

PKG_MAINTAINER := Felix Fietkau <nbd@nbd.name>

include $(INCLUDE_DIR)/package.mk

define Package/usbutils
  SECTION:=utils
  CATEGORY:=Utilities
  DEPENDS:=+libusb-1.0 +librt +libpthread
  TITLE:=USB devices listing utilities
  URL:=http://www.linux-usb.org/
endef

USB_IDS_REV:=ae25707c751fff79148328229a76fc44232abeae
USB_IDS_FILE:=usb.ids.$(USB_IDS_REV)
define Download/usb_ids
  FILE:=$(USB_IDS_FILE)
  URL_FILE:=usb.ids
  URL:=@GITHUB/gentoo/hwids/$(USB_IDS_REV)
  HASH:=eca5d4b4b2c72e61d5d6d67b5dc6f75e92b4ac9cf9cdf1344f06622e0f57d82f
endef
$(eval $(call Download,usb_ids))

define Build/Prepare
	$(Build/Prepare/Default)
	$(CP) $(DL_DIR)/$(USB_IDS_FILE) $(PKG_BUILD_DIR)/usb.ids
endef

CONFIGURE_ARGS += \
	--disable-zlib

define Package/usbutils/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/lsusb $(1)/opt/bin/
	$(INSTALL_DIR) $(1)/opt/share
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/opt/share/usb.ids $(1)/opt/share/
endef

$(eval $(call BuildPackage,usbutils))
