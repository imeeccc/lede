#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/kernel.mk

PKG_NAME:=exfat
<<<<<<< HEAD
PKG_VERSION:=5.8.4
=======
PKG_VERSION:=5.8.7
>>>>>>> upgrade/master
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/namjaejeon/linux-exfat-oot/tar.gz/$(PKG_VERSION)?
<<<<<<< HEAD
PKG_HASH:=47162495bdf9a7e02d6142dfcd4364d7325a4cf75a0439926cf9e8a9d959627b
=======
PKG_HASH:=20254677bed3f456e89cc9d757c1a47abbadab4d75640eef4a995370a37be3f4
>>>>>>> upgrade/master

PKG_MAINTAINER:=
PKG_LICENSE:=GPL-2.0-only

<<<<<<< HEAD
#PKG_BUILD_PARALLEL:=1
#PKG_USE_MIPS16:=0

# exfat-oot's makefile needs this to know where to build the kernel module
#export KERNELDIR:=$(LINUX_DIR)

include $(INCLUDE_DIR)/package.mk
#include $(INCLUDE_DIR)/kernel-defaults.mk
=======
include $(INCLUDE_DIR)/package.mk
>>>>>>> upgrade/master

TAR_OPTIONS+= --strip-components 1
TAR_CMD=$(HOST_TAR) -C $(1) $(TAR_OPTIONS)

define KernelPackage/fs-exfat
  SECTION:=kernel
  CATEGORY:=Kernel modules
  SUBMENU:=Filesystems
  TITLE:=exFAT kernel module
  FILES:=$(PKG_BUILD_DIR)/exfat.ko
  AUTOLOAD:=$(call AutoProbe,exfat)
  DEPENDS:=+kmod-nls-base
endef

define KernelPackage/exfat/description
  This package provides the kernel module for exfat.
endef

define Build/Compile
	$(KERNEL_MAKE) M="$(PKG_BUILD_DIR)" \
	EXTRA_CFLAGS="$(EXTRA_CFLAGS)" \
	$(PKG_EXTRA_KCONFIG) \
	CONFIG_EXFAT_FS=m \
	modules
<<<<<<< HEAD
#	$(MAKE) -C $(KERNEL_BUILD_DIR)/linux-$(LINUX_VERSION) M="$(PKG_BUILD_DIR)" modules
=======
>>>>>>> upgrade/master
endef

$(eval $(call KernelPackage,fs-exfat))
