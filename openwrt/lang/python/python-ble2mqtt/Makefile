#
# Copyright (C) 2026
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
include $(TOPDIR)/rules.mk

PKG_NAME:=python-ble2mqtt
PKG_VERSION:=0.2.5
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/ru-admin/ble2mqtt.git
PKG_SOURCE_VERSION:=$(PKG_VERSION)
PKG_SOURCE_DATE:=2026-09-17
PKG_MIRROR_HASH:=skip

PYTHON3_PKG_WHEEL_NAME:=ble2mqtt
PYTHON3_PKG_WHEEL_VERSION:=$(PKG_VERSION)

PKG_BUILD_DEPENDS:=python3/host python3-build/host python3-installer/host

PKG_MAINTAINER:=ru-admin
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

include $(INCLUDE_DIR)/package.mk
include ../python3-package.mk

define Package/python3-ble2mqtt
  SECTION:=lang
  CATEGORY:=Languages
  SUBMENU:=Python
  TITLE:=Bluetooth to MQTT bridge
  URL:=https://github.com/ru-admin/ble2mqtt/
  DEPENDS:=+python3-light +python3-aio-mqtt-mod +python3-asyncio +python3-bleak +python3-logging +python3-uuid
endef

define Package/python3-ble2mqtt/description
  Bluetooth to MQTT bridge, add your bluetooth-capable (including controllable)
  devices to your smart home
endef

define Py3Package/python3-ble2mqtt/install
	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) ./files/ble2mqtt.init $(1)/etc/init.d/ble2mqtt
	$(INSTALL_DIR) $(1)/usr/bin
	$(CP) $(PKG_INSTALL_DIR)/usr/bin/* $(1)/usr/bin/
endef

$(eval $(call Py3Package,python3-ble2mqtt))
$(eval $(call BuildPackage,python3-ble2mqtt))
$(eval $(call BuildPackage,python3-ble2mqtt-src))