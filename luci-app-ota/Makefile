
include $(TOPDIR)/rules.mk

LUCI_TITLE:=LuCI for OTA upgrade
LUCI_PKGARCH:=all
LUCI_DEPENDS:=+fw_download_tool +jsonfilter
PKG_VERSION:=1.2
PKG_RELEASE:=1
PKG_MAINTAINER:=jjm2473 <jjm2473@gmail.com>

include $(TOPDIR)/feeds/luci/luci.mk

define Package/$(PKG_NAME)/install
	# 安装 LuCI 控制器
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/controller/admin
	$(INSTALL_DATA) ./luasrc/controller/admin/ota.lua $(1)/usr/lib/lua/luci/controller/admin/ota.lua

	# 安装 LuCI 页面
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/view/admin_system
	$(INSTALL_DATA) ./luasrc/view/admin_system/ota.htm $(1)/usr/lib/lua/luci/view/admin_system/ota.htm
	$(INSTALL_DATA) ./luasrc/view/admin_system/ota_flashing.htm $(1)/usr/lib/lua/luci/view/admin_system/ota_flashing.htm

	# 安装翻译文件
	$(INSTALL_DIR) $(1)/usr/lib/lua/luci/i18n
	po2lmo ./po/zh_Hans/ota.po $(1)/usr/lib/lua/luci/i18n/ota.zh_Hans.lmo

	# 安装 /bin/ota 可执行文件
	$(INSTALL_DIR) $(1)/bin
	$(INSTALL_BIN) ./root/bin/ota $(1)/bin/ota

	# 安装 UCI 配置文件
	$(INSTALL_DIR) $(1)/etc/config
	$(INSTALL_CONF) ./root/etc/config/ota $(1)/etc/config/ota
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
