# month5
产出记录: 20250206-20250304

## RuyiSDK 支持矩阵相关

### PRs 
- [Add/Update mangopi_mq_pro (1)](https://github.com/ruyisdk/support-matrix/pull/134)
- [Add TTGO T-Display-GD32 board & Add μC/OS-II](https://github.com/ruyisdk/support-matrix/pull/169)
- [Ports documentation from oscompare](https://github.com/ruyisdk/support-matrix/pull/163)

新增**开发板观测**：
- MangoPi MQ Pro
- Lilygo TTGO T-Display-GD32

新增**操作系统观测**：
- Slackware
- postmarketOS
- μC/OS-II

### 内容详细
总计新增7+4篇，更新7篇。

**新增**测试报告：
- MangoPi MQ Pro
  - Slackware
  - postmarketOS
- Lilygo TTGO T-Display-GD32
  - FreeRTOS
  - RT-Thread
  - ThreadX
  - μC/OS-II
- Sipeed Longan Nano
  - μC/OS-II

**更新**测试报告（原 CFT）：
- MangoPi MQ Pro
    - Armbian (CFH)
    - ArchLinux (CFH)
    - Debian
    - Fedora
    - OpenWrt
    - Ubuntu
    - openSUSE

同时正在移植上月的 oscompare 任务中产出的测试报告 (主要工作为翻译至英文)：

- Deepin @ BPI-F3
- Deepin @ Pioneer
- Deepin @ Unmatched
- openKylin @ BPI-F3 

## 其他

通过修改 dts 测试了 Zephyr 在 Lilygo TTGO T-OI-Plus 上的可用性，并为 Zephyr 项目提交了 PR：[boards: lilygo: t_oi_plus: initial support](https://github.com/zephyrproject-rtos/zephyr/pull/86486)

等待合并后可写入支持矩阵中。