include $(TOPDIR)/rules.mk
include $(INCLUDE_DIR)/version.mk

PKG_NAME:=wav500-images
PKG_VERSION:=1
PKG_RELEASE:=2
PKG_LICENSE:=GPL-2.0

PKG_MAINTAINER:=paldier <paldier@hotmail.com>
PKG_BUILD_DIR:=$(BUILD_DIR)/$(PKG_NAME)-$(PKG_VERSION)

#k3cb1=k3cb1g=k3cc1,k3ca1=k3cb2
 WAVE_TARGET:=k3c
ifeq ($(CONFIG_TARGET_lantiq_xrx500_k3c),y)
 WAVE_TARGET:=k3c
endif
ifeq ($(CONFIG_TARGET_lantiq_xrx500_k3ca1),y)
 WAVE_TARGET:=k3cv2
endif
ifeq ($(CONFIG_TARGET_lantiq_xrx500_k3cv2),y)
 WAVE_TARGET:=k3cv2
endif
ifeq ($(CONFIG_TARGET_lantiq_xrx500_k3cc1),y)
 WAVE_TARGET:=k3c
endif
ifeq ($(CONFIG_TARGET_lantiq_xrx500_k3cp),y)
 WAVE_TARGET:=k3c
endif
ifeq ($(CONFIG_TARGET_lantiq_xrx500_bluecave),y)
 WAVE_TARGET:=bluecave
endif
ifeq ($(CONFIG_TARGET_lantiq_xrx500_easy350_anywan_800m_owrt),y)
 WAVE_TARGET:=k3c
endif

include $(INCLUDE_DIR)/package.mk

define Package/wav500-images
  SECTION:=utils
  CATEGORY:=Lantiq
  TITLE:=Wav500 WiFi driver images
  DEPENDS:=@TARGET_lantiq_xrx500
endef

define Package/$(PKG_NAME)/description
Wav500 WiFi driver images
endef

define Build/Prepare
endef

define Build/Compile
endef

define Package/wav500-images/install
	$(INSTALL_DIR) -p $(1)/lib/firmware $(1)/etc/init.d
	$(INSTALL_BIN) ./files/$(WAVE_TARGET)/* $(1)/lib/firmware/
	$(INSTALL_BIN) ./files/etc/$(WAVE_TARGET)/wifi_start.sh $(1)/etc/init.d/
endef

$(eval $(call BuildPackage,wav500-images))
