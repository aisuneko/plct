# month4
产出记录: 20250101-20250127

## RuyiSDK 支持矩阵相关

### PRs 
- [duo/duo256m: update Buildroot to V2](https://github.com/ruyisdk/support-matrix/pull/134)
- [visionfive2: Add Fedora](https://github.com/ruyisdk/support-matrix/pull/142)
- [duo/duo256m: Add NixOS](https://github.com/ruyisdk/support-matrix/pull/157)

### 内容详细

**新增**测试报告：
- Fedora (V Force) @ VisionFive 2
- NixOS @ Milk-V Duo
- NixOS @ Milk-V Duo 256M

**更新**测试报告：
- BuildRoot (V2) @ Milk-V Duo 
- BuildRoot (V2) @ Milk-V Duo 256M

其中 NixOS 测试系通过修改原 repo 中的 nix 配置文件实现，PR 见 https://github.com/NickCao/nixos-riscv/pull/24

## 测试报告任务

### RISC-V 操作系统对比报告

进行了下列测试，同时参与撰写了测试报告并提供了截图：
- [openAnolis @ QEMU](https://github.com/QA-Team-lo/oscompare/tree/main/openAnolis/QEMU)
- [openEuler @ Pioneer](https://github.com/QA-Team-lo/oscompare/blob/main/openEuler/Pioneer/README.md)
- [openKylin @ Pioneer](https://github.com/QA-Team-lo/oscompare/tree/main/openKylin/Pioneer)

### RT-Thread fork
尝试在 Duo/Duo256M 上测试 https://github.com/plctlab/plct-rt-thread/tree/master 失败，向项目负责人反馈了问题：[[Bug] Image built for Milk-V Duo/Duo256M fails to boot from SD card](https://github.com/RT-Thread/rt-thread/issues/9904)