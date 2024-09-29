# pretask & month0
产出记录: 20240815-20240823 (pretask), 20240906-20240929 (第一月)

周报（英文）：[pretask](week0/testround.md) / [week1](week1/week1.md) / [week2](week2/week2.md) / [week3](week3/week3.md) / [week4](week4/week4.md)
## 软件包自动化测试工具 lintestor
从 pretask 开始参与了 lintestor 的开发。pretask 阶段做了大量的框架重构、测试脚本重写和问题修复，正式入职后则帮助实现了数个新功能，编写使用文档，issues协作和进行了其他维护工作。

### 代码重构，问题修复及优化
- [首个 PR](https://github.com/255doesnotexist/lintestor/pull/1/)：[8 commits](https://github.com/255doesnotexist/lintestor/pull/1/commits)
  - 修正 `--locally` 选项的行为， 增加 `--verbose`  选项
  - 重构了测试报告生成相关代码，从框架本身而不是测试脚本生成测试报告
  - 基于上一项，重写了 `debian` 目录下的所有测试报告
  - 进行了其他代码重构和bug修复，提升了项目可用性

- bug 修复: [1](https://github.com/255doesnotexist/lintestor/commit/e2ef1a728d6e7187284cb7be608982fa05cfb649), [2](https://github.com/255doesnotexist/lintestor/commit/9e7791e8082ea6027300387eaff1b1167022b561), [3](https://github.com/255doesnotexist/lintestor/commit/7020cd57a84ac2ed3e49aaf7ad3558401f34d837)
- linting 及其他小幅更改: [1](https://github.com/255doesnotexist/lintestor/commit/3afae63ed25a7e49eedb0ad56aba934e35186bae), [2](https://github.com/255doesnotexist/lintestor/commit/3f577ddf10279f2576ad2bc13acaa98ca088b01e), [3](https://github.com/255doesnotexist/lintestor/commit/ce21f2e7c21ad6e5c155c5e61b72cfbc613a0087), [4](https://github.com/255doesnotexist/lintestor/commit/573aee80cf2868d8c2b05eb14ec475497cdd487d)
### 新特性
- 使用 `env_logger` 重写了日志输出部分: [1](https://github.com/255doesnotexist/lintestor/commit/dd6bcd832ca66005206d515613cf02e5c3a18420)
- **增加软件包独立元数据支持**: [1](https://github.com/255doesnotexist/lintestor/commit/5c7189e415bb498d3ef24af1520ab86a618f1b13)
  - 响应 RuyiSDK 组会上提出的需求，目前支持显示软件包正式名称 (pretty name)， 包版本，包类型等字段，使用测试脚本目录下定义的 `metadata.sh` 实现
- 大幅填充和优化了 Markdown 总测试报告(矩阵)的输出内容和格式：[1](https://github.com/255doesnotexist/lintestor/commit/2e78791eee4ae20a33c8c333a4034083e011334e), [2](https://github.com/255doesnotexist/lintestor/commit/71a9397ce4292f02ae97025b4487d3808bf53696)
### 文档编写
- 编写和更新使用指南 USAGE.md (中文) 和 USAGE_en.md (英文)：[1](https://github.com/255doesnotexist/lintestor/commit/f79a6ac36375c7811e48cd951c4bfa090f83c8d8), [2](https://github.com/255doesnotexist/lintestor/commit/8381c435c032437278aa793138c4cbee97479151), [3](https://github.com/255doesnotexist/lintestor/commit/f9d4acf9965d444aec8fd469c6f2a8ffc53464c8), [4](https://github.com/255doesnotexist/lintestor/commit/80dbf70c5b2c2ea3c704a806b72e1d05344ee1ec), [5](https://github.com/255doesnotexist/lintestor/commit/5d7fb9f1f998a0eb6c6f320e389251c4fcf68082)
- README 更新和其他小幅改动: [1](https://github.com/255doesnotexist/lintestor/commit/4d19c7170f87be971aacf2ebb8de57340ed723a4), [2](https://github.com/255doesnotexist/lintestor/commit/97f9b8a400ade39ac8d4fb993d8b23fb33be9461), [3](https://github.com/255doesnotexist/lintestor/commit/6fc4aff90fcbd400b6ce2f4b2391be5b73f42324)
### 协作
- 在 Milk-V Duo S 上使用开发版本的 lintestor 运行了软件包测试 (测试结果见 [testround.md](week0/testround.md))
- 通过 Issues 进行协作: assigned to and closed [#6](https://github.com/255doesnotexist/lintestor/issues/6), [#13](https://github.com/255doesnotexist/lintestor/issues/13), [#20](https://github.com/255doesnotexist/lintestor/issues/20)

## RuyiSDK 支持矩阵相关
### 文档
**帮助校对了 ruyisdk/support-matrix 中的所有现有测试报告，支持矩阵表格和文档:** 2 merged PRs [#37](https://github.com/KevinMX/support-matrix/pull/37), [#39](https://github.com/KevinMX/support-matrix/pull/39): 5 commits

- 校正开发板文档中的操作系统版本信息
- 校对了所有开发板的支持状态信息
- 补充了支持矩阵表格中遗漏的 Yocto 发行版相关信息
- 补充了支持矩阵表格中遗漏的 CM32M433R, R128-EVT 等已测试的开发板的信息
- 其他 typo 修复和改正

### 测试
**在 Milk-V Duo 256M 上成功运行 Alpine Linux 3.20.3 riscv64**
- 通过使用 Fishwaldo Debian 镜像中的内核和内核模块，手工从 Alpine minirootfs 构建 bootable rootfs 并替换的方式实现
- 提交了测试报告：PR [board/Duo256M: Add Alpine Linux](https://github.com/KevinMX/support-matrix/pull/42)

## Demo
- 在 Milk-V Duo 256M 上实现了基于 MobileNet-Caffe 模型的图像分类
  - 基于厂商 TPU SDK 实现，使用转换成 MLIR 格式并 INT8 量化后的 [MobileNetv2 Caffe](https://github.com/shicai/MobileNet-Caffe) 模型实现
  - [详细文档（英文）](week2/demo_duo256_mobilenet.md)

- 在 Milk-V Duo 256M 上尝试编译运行 [llama.cpp](https://github.com/ggerganov/llama.cpp)，发现无法运行
  - gdb 调试发现是因为 `llama.cpp` 在 RISC-V 平台上需要 v 扩展并默认针对 rvv 1.0 编译。调研发现 Duo 256M 使用的 SG2002 SoC 仅支持 rvv 0.7.1；尝试使用 `-march=rv64gc_xtheadvector` 编译未果，故暂时认为 `llama.cpp` 不支持在该芯片上运行
  - 详细报告见 [week3 周报（英文）](week3/week3.md)

## 其他
- 在 Milk-V Duo S 上试用了 [255doesnotexist/boardtest](https://github.com/255doesnotexist/boardtest) 并为其添加了 Duo S 相关配置支持：PR [add support for Milk-V Duo S & Debian test target](https://github.com/255doesnotexist/boardtest/pull/1)
- 在 Milk-V Duo S (Debian) 上成功运行 Docker
  - 观察报错发现 Fishwaldo Debian 镜像中的内核缺少 cgroup/BPF/veth 相关编译选项，需要在 defconfig 中开启相关选项后手动编译内核并替换
  - 详细报告见 [pretask 产出（英文）中的 task3 部分](week0/testround.md)

## 未来计划
- 继续维护 lintestor 并添加更多新功能
- 在 Duo 256M 上尝试运行一个 LM 相关 demo
- 基于上面的 Alpine 适配构建一个可用镜像，并探讨在 RuyiSDK 支持矩阵中引入 Alpine Linux 观测的可能性
- 在更多开发板上进行测试