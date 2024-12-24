# OC_B760M_AX101_6750GRE

## 展示

<img width="392" alt="图片" src="https://github.com/user-attachments/assets/735a3310-71db-4530-a41c-e97353f08f34">


## 配置

- CPU i5 12600KF 6大核4小核 10核16线程 无核显
- 主板 铭瑄B760M终结者 D5 WiFi
- 内存 玖合 DDR5 5600Mhz 16G * 2
- 固态 致钛 TiPlus 7100 1T
- 网卡
  - 板载有线网卡
  - Intel AX101
- 显卡 蓝宝石6750GRE 12G 白金版

- 系统 **Sonoma 14.7** / **Sequoia 15.2**

## 功能情况

- [x] 大小核
- [x] WiFi
- [x] 蓝牙
- [x] 网线
- [x] 独立显卡与H265、H264硬解
- [x] USB除了板载第一排屏蔽了，其他都正常（因为第一排是HUB，会导致有时USB失效）
- [x] 睡眠（睡到内存风扇断电与USB键鼠可唤醒）
- [ ] 无法开启网络共享（热点）
- [ ] 无法休眠（睡到硬盘，主机断电，开机时从硬盘恢复内存状态）

## BIOS设置

- 关闭以下选项
  - 快速启动
  - 支持CSM
  - 安全启动
  - VT-d
  - CFG Lock **必须要关**
- 启用以下选项
  - 4G以上解码
  - 超线程技术
  - EHCI/XHCI Hand-off

## Sequoia配置Intel WiFi 蓝牙

1. 关闭SIP（我给的EFI里已经关了，如果你没关自行关闭）
2. 清除NVRAM （在启动到OC选择系统的时候，按空格会显示清除NVRAM的选项），这个操作会清掉OC的UEFI启动项，重新添加即可。

3. 下载 [OCLP-Mod](https://github.com/laobamac/OCLP-Mod) 并安装，打开后点击**安装驱动补丁**
4. 重启后WiFi蓝牙正常。（蓝牙打不开就清除NVRAM）

## 其他

不要直接下[NootRX](https://github.com/ChefKissInc/NootRX/actions/workflows/main.yml)的最新版，说不定就有什么bug，用别人EFI里的都是他用着没问题的。我就是因为显卡驱动bug导致唤醒后系统卡顿，卡了两天才排查出来。
