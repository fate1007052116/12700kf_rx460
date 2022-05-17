## 

### RX 460显示RX 460/560 没有功能集
> 参考：https://bbs.pcbeta.com/viewthread-1862688-1-1.html
>      https://bbs.pcbeta.com/viewthread-1847847-1-4.html
#### 1、设置显卡型号
config.plist 配置
在`DeviceProperties`下添加
```plist

		<dict>
			<key>PciRoot(0x0)/Pci(0x1,0x0)/Pci(0x0,0x0)</key>
			<dict>
				<key>model</key>
				<string>Radeon RX 460</string>
			</dict>
		</dict>

```

#### 2、性能增强
我没有CPU核显和有 AMD 显卡的用户：可以在 boot-args 中手动加入 cardtype=ecardonly，提升独显的工作效率。

```plist
			<key>7C436110-AB2A-4BBB-A880-FE41995C9F82</key>
			<dict>
				<key>SystemAudioVolume</key>
				<data>Rg==</data>
				<key>boot-args</key>
				<string>-v keepsyms=1 debug=0x100 agdpmod=pikera -wegnoigpu alcid=66  cardtype=ecardonly</string>
				<key>csr-active-config</key>
				<data>AAAAAA==</data>
				<key>run-efi-updater</key>
				<string>No</string>
			</dict>

```