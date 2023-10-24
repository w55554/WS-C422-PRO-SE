## 机型配置如下
|硬件|厂商和配置|
|-|-|
|主板|华硕 WS C422 PRO/SE(c422芯片组)|
|CPU| Intel Xeon W-2150B|
|内存|64G(2*32G REG ECC 2933 MHz SK Hynix内存条，实际受到我的CPU限制，频率只有2666)|
|显卡|华硕角斗士STRIKER-GTX 760-P-4GD5 (NVIDIA GeForce GTX 760)|
|网卡|2 * Intel I210 Gigabit network connection |
|WIFI|Intel Dual Band Wireless-AC 7625|
|蓝牙|版本4.2|
|声卡|S1220A 声卡(我的声卡ID选择的是21)|
|MacOS盘|Kingston A400 240G SATA 固态硬盘|
|硬盘2|三星 SSD 980 500G M.2 NVME 固态|
|硬盘3|西部数据 SN520 500G M.2 NVME 固态|
|硬盘4|希捷 2T 机械硬盘|
## 相关资料
声卡支持: https://github.com/acidanthera/AppleALC/wiki/Supported-codecs

无线网卡: https://www.intel.cn/content/www/cn/zh/products/sku/83635/intel-dual-band-wirelessac-7265/specifications.html

OC向导: https://dortania.github.io/OpenCore-Install-Guide/prerequisites.html

## BIOS设置  
**How to Setting Bios**    
- /AI Tweaker/  
a.) ASUS MultiCore Enhancement: Auto   
b.) AVX Instruction Core Ratio Negative Offset: "3"   
c.) AVX-512 Instruction Core Ratio Negative Offset: "2"   
d.) CPU Core Ratio: Sync All Cores  
e.) CPU SVID Support: Enabled   
f.) DRAM Frequency: DDR4-3200MHz (in my particular case)

- /Advanced/CPU Configuration/  
a.) Hyper Threading [ALL]: Enabled  
b.) MSR Lock Control: Disabled 

- /Advanced/CPU Configuration/CPU Power Management Configuration/  
a.) Enhanced Intel Speed Step Technology (EIST): Enabled  
b.) Autonomous Core C-States: Enabled  
c.) Enhanced Halt State (C1E): Enabled  
d.) CPU C6 report: Enabled  
e.) Package C-State: C6(non retention) state  
f.) Intel SpeedShift Technology: Enabled  
g.) MFC Mode Override: OS Native  

- /Advanced/Platform Misc Configuration/    
a.) PCI Express Native Power Management: Disabled  
b.) PCH DMI ASPM: Disabled  
d.) ASPM: Disabled  
e.) DMI Link ASPM Control: Disabled  
f.)  PEG - ASMP: Disabled  

- /Advanced/System Agent Configuration/  
a.) Intel VT for Directed I/O (VT-d): Disabled/Enabled  

- /Boot/  
a.) Fast Boot: Disabled  
b.) Above 4G Decoding: Off (must be ON with Prime X299 Deluxe BIOS firmware 1603 and 1704 and WS X299 Sage 10G BIOS firmware 0905 in case of GPU firmware load and XHCI ACPI implementation issues. When employing WS X299 Sage 10G BIOS firmware 0905 and enabling Above 4G Decoding in the respective BIOS settings as required, "First VGA 4G Decode" must be set to "Auto", as both Windows 10 and macOS can become irresponsive with different "First VGA 4G Decode" settings.  
c.) Set your specific Boot Option Priorities  
 
- /Boot/Boot Configuration  
a.) Boot Logo Display: Auto   
b.) Boot up NumLock State: Disabled  
c.) Setup Mode: Advanced  
 
- /Boot/Compatibility Support Module/  
a.) Launch CSM: Disabled  
 
- /Boot/Secure Boot/  
a.) OS Type: Other OS  

## 安装系统
- OC版本  
  OC的版本选择的是0.7.8
- 系统版本
<details><summary>Monterey 12.6(21G115) - 2022.09.12</summary>
系统下载地址: https://heipg.cn/macos/macos-monterey-12-6-21g115.html
</details>

<details><summary>BigSur 11.7.10(20G1427) - 2023.09.11</summary>
BUG: 
1、目前测试蓝牙有问题，可能链接不上设备
2、休眠的时候，CPU风扇一直在反复的停转
系统下载地址:https://heipg.cn/macos/macos-big-sur-11-7-10-20g1427.html  
 
![big sur picture](https://github.com/w55554/WS-C422-PRO-SE/blob/main/images/big_sur.png)
![nvme](https://github.com/w55554/WS-C422-PRO-SE/blob/main/images/nvme.png)
![sata](https://github.com/w55554/WS-C422-PRO-SE/blob/main/images/sata.png)
![pci](https://github.com/w55554/WS-C422-PRO-SE/blob/main/images/pci.png)
![wifi](https://github.com/w55554/WS-C422-PRO-SE/blob/main/images/wifi.png)
![ethernet](https://github.com/w55554/WS-C422-PRO-SE/blob/main/images/ethernet.png)
</details>
