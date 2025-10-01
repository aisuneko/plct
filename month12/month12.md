# month12

产出记录：20250902-20250930

# RuyiSDK 测试矩阵

新增了对 Tizen 的观测，及 MangoPi MQ 的相关测试。

因测试用的 MangoPi MQ 上电仅能进入 FEL 模式，无法测试除 RT-Thread 和 xv6 外的其他系统。

- Tizen @ VisionFive2
- Tizen @ LicheePi4A (CFT)
- Tizen @ BPI-F3 (CFT)
- xv6 @ MangoPi MQ (CFH)
- TinaLinux @ MangoPi MQ (CFH)
- RT-Thread @ MangoPi MQ

PRs:

[Add Tizen](https://github.com/ruyisdk/support-matrix/pull/368)

[Update mangopi_mq](https://github.com/ruyisdk/support-matrix/pull/371)

# Opennovation 系列测试

完成了对如下软件包 在 Milk-V Pioneer (RevyOS) 上的编译验证，测试，及中英文报告编写工作：

- EM/Meep
- EM/Tessa
- EM/MPB
- ICME/abinit
- ICME/LAMMPS
- MBD/MBDyn
- MBD/ORSA
- Plumbing

PRs: https://github.com/QA-Team-lo/engineering-riscv/pull/4, https://github.com/QA-Team-lo/engineering-riscv/pull/10

# ruyisdk.cn 论坛

发布了 3 篇支持矩阵内容介绍帖子：

[RISC-V MCU 漫游 (7)：黄紫色的 ESP32 之 ESP32-C2/C6](https://ruyisdk.cn/t/topic/1441)

[RISC-V MCU 漫游 (8)：Kendryte K210](https://ruyisdk.cn/t/topic/1557)

[Pine64 RISC-V 开发板介绍 (1)：Ox64](https://ruyisdk.cn/t/topic/1613)

# 其他

完成了全志 V821 文档（https://docs.aw-ol.com/docs/soc/v821/）的校对和 Review 任务的内部交付。