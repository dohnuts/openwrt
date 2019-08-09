include $(TOPDIR)/rules.mk

PKG_NAME:=hd53-firmware
PKG_RELEASE:=1
PKG_FLAGS:=nonshared

PKG_MAINTAINER:=Citypassenger <sf@citypassenger.com>

include $(INCLUDE_DIR)/package.mk

define Package/hd53-firmware
  PKGARCH:=all
  SECTION:=firmware
  CATEGORY:=Firmware
  URL:=https://github.com/dohnuts/openwrt
  TITLE:=Board Data for HD53
endef

DEPENDS:=@TARGET_ipq40xx,ipq-wifi

define Build/Compile
	echo "OK"
endef


define Package/hd53-firmware/install
	$(INSTALL_DIR) $(1)/lib/firmware/ath10k/QCA9888/hw2.0
	$(INSTALL_DIR) $(1)/lib/firmware/ath10k/QCA4019/hw1.0
	$(INSTALL_DATA) ./files/board.bin $(1)/lib/firmware/ath10k/QCA9888/hw2.0/board.bin
	$(INSTALL_DATA) ./files/firmware-5.bin $(1)/lib/firmware/ath10k/QCA9888/hw2.0/firmware-5.bin
	$(INSTALL_DATA) ./files/board.bin $(1)/lib/firmware/ath10k/QCA4019/hw1.0/board.bin
	echo "OK"
endef

$(eval $(call BuildPackage,hd53-firmware))
