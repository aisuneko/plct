# month9

产出记录：20250531-20250630

## support-matrix

### PRs

[Miscellaneous tests bump](https://github.com/ruyisdk/support-matrix/pull/326)

### 报告详细

新增 8 篇：
- Zephyr @ CH32V003
- Zephyr @ TTGO T-OI-Plus
- postmarketOS @ Sipeed M1s Dock (CFH)
- RT-Thread @ Sipeed M0P Dock
- RT-Thread @ Sipeed M1s Dock (CFH)
- RT-Thread @ MangoPi MQ-Pro
- RT-Thread @ DongshanPI Nezha-STU
- FreeBSD @ VisionFive2 (CFH)

更新 2 篇：
- BuildRoot @ Sipeed M1s Dock (CFH)
- xv6 @ MangoPi MQ-Pro (edit)

## lintestor

对新版本进行了一系列的重大bug修复和维护工作。

[fix: target config probing](https://github.com/255doesnotexist/lintestor/pull/96/commits/82296ea42f43d7e81d6f9ae7487f58c12c1882d1)

[fix: deduplicate discovered template paths](https://github.com/255doesnotexist/lintestor/pull/96/commits/c33195de2337569a2f1863216f6adb8b74cb0314)

[fix: proper serial session handling](https://github.com/255doesnotexist/lintestor/commit/3538489c612dcbbfc17fb1dfc5138a0cf78abf94)

chores (clippy, file cleanup)

## ruyisdk-gnu-tests

正在进行 GCC 15 在 K230 上的测试，使用 lintestor 完成（边使用边开发）。