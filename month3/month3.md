# month3
产出记录: 20241130-20241226

周报（英文）：[week0](week0/week0.md) / [week1](week1/week1.md) / [week2](week2/week2.md) / [week3](week3/week3.md)
## 软件包自动化测试工具 lintestor

- [docs: update usage](https://github.com/255doesnotexist/lintestor/commit/db9aaeb6d9ff33c09fc2e12e6dda04c3abd8e74d)
- 一些其他 chores

## RuyiSDK 支持矩阵相关

进行了 Sipeed Longan Nano / LicheeRV Nano / M0Sense，Starfive VisionFive 2，Milk-V Duo / Duo256M 在合计 7 个发行版/RTOS 上的可用性测试，共新撰写 5 篇报告，更新 3 篇报告，2 个测试未成功：

### PRs 
- [longan_nano: add FreeRTOS/RT-Thread/ThreadX](https://github.com/ruyisdk/support-matrix/pull/97)
- [licheervnano: Add/Update Alpine/BuildRoot/Fedora](https://github.com/ruyisdk/support-matrix/pull/119)
- [visionfive2: Add NixOS](https://github.com/ruyisdk/support-matrix/pull/123)
- [duo256m: Update Alpine & RT-Thread Smart](https://github.com/ruyisdk/support-matrix/pull/109)
- [m0sense: Add RT-Thread](https://github.com/ruyisdk/support-matrix/pull/125)

### 内容详细

**新增**测试报告：
- ThreadX @ Longan Nano
- Alpine @ LicheeRV Nano
- Fedora @ LicheeRV Nano
- NixOS @ VisionFive 2
- RT-Thread @ M0sense

**更新**测试报告：
- FreeRTOS @ Longan Nano (CFT -> Basic)
- RT-Thread @ Longan Nano (CFT -> Basic)
- BuildRoot @ LicheeRV Nano

### 测试未成功

- NixOS @ Duo
- NixOS @ Duo 256M

因 nixpkgs 工具链版本过低而编译失败，可能需要等待 nixpkgs 推送 GCC 14

Issue: [[Page Content] NixOS for Duo/Duo256M failed to build](https://github.com/ruyisdk/support-matrix/issues/124)

## 测试报告任务
- 校对，优化排版，润色和书面化 openGauss 测试报告：[commit](https://github.com/QA-Team-lo/dbtest/commit/89410b6eb39c46c1c67e64c55d001bdb6db43fc3)
- 校对，优化排版，润色和书面化 OceanBase 测试报告：[commit](https://github.com/QA-Team-lo/dbtest/commit/fd2070e292fc6c78316abe4eb36787b9cba308fcf)