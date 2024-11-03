<div align="center">
<h1 align="center">同步上游分支代码</h1>
<img src="https://img.shields.io/github/issues/wixxm/wikjxwrt-packages?color=green">
<img src="https://img.shields.io/github/stars/wixxm/wikjxwrt-packages?color=yellow">
<img src="https://img.shields.io/github/forks/wixxm/wikjxwrt-packages?color=orange">
<img src="https://img.shields.io/github/license/wixxm/wikjxwrt-packages?color=ff69b4">
<img src="https://img.shields.io/github/languages/code-size/wixxm/wikjxwrt-packages?color=blueviolet">
</div>


#### 🏅 Github 🏅
 ![kenzo_github_stats](https://github-readme-stats.vercel.app/api?username=wixxm&show_icons=true&theme=merko)

#### 🎉 WikjxWrt-Packages 🎉
*  适用于openwrt 22.03 及以上的分支
 
*  所有插件都为网上收集的开源插件,感谢作者们的付出.

*  常用OpenWrt软件包源码合集，同步上游更新！

*  关于有好的插件请在issues提交

*  再次感谢以上github仓库所有者！
#### 🌈 使用方式 🌈

```bash
 sed -i '$a src-git wikjxwrt https://github.com/wixxm/wikjxwrt-packages' feeds.conf.default
```
#### 🛸 特别注意 🛸
*  使用Openwrt23.05.5(快照版除外，其他版本没有测试)官方源码编译luci-app-passwall时，需要把golang切换为最新版，否则会出现一些插件编译失败。
  ```shell
rm -rf feeds/packages/lang/golang
git clone https://github.com/wixxm/WikjxWrt-golang feeds/packages/lang/golang
```

*  使用Openwrt23.05官方源码编译luci-app-passwall插件时，需要将make menuconfig配置中取消dnsmasq保留dnsmasq-full避免冲突。


