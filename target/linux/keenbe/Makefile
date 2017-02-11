#
# Copyright (C) 2011-2017 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

ARCH:=mips
CPU_TYPE:=mips32r2
BOARD:=keenbe
BOARDNAME:=Keenetic (mips be, soft float)
FEATURES:=
KERNEL_PATCHVER:=2.6.22
DEFAULT_PACKAGES := toolchain

include $(INCLUDE_DIR)/target.mk

define Target/Description
	Build Software Repository for MIPS soft float routers.
endef

$(eval $(call BuildTarget))
