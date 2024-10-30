# month1
产出记录: 20240930-20241030
周报（英文）：[week0](week0/week0.md) / [week1](week1/week1.md) / [week2](week2/week2.md) / [week3](week3/week3.md)
## 软件包自动化测试工具 lintestor
### 新特性
#### 命令行参数
- 添加了 `--skip-successful`, `--distro`, `--package` 参数 ([1](https://github.com/255doesnotexist/lintestor/commit/f91085286b731514facb629cf33c189458ae0a9f), [2](https://github.com/255doesnotexist/lintestor/commit/f78035383a71b031cc37de4eaa763882e524cf4e))
- 添加了其他已有参数的短形式：[3](https://github.com/255doesnotexist/lintestor/commit/3a7e0ba95dfbfe1fba9619c16a43f2670143de05)

### 整合测试
使用 `assert_cmd` 实现整合测试， 测试方式为模拟手动执行 `./lintestor -tas` 的行为，并添加对应的测试样例：[PR](https://github.com/255doesnotexist/lintestor/pull/33), 4 commits

### 代码重构，问题修复及优化
- 重写了测试文件识别逻辑，取消 root config 改为自动探测指定工作目录下的已配置测试：([1](https://github.com/255doesnotexist/lintestor/commit/acf634fd2c59859ca5cf3fc31cc3e63256258526))
- 使用 `Path`/`PathBuf` 代替原先的硬编码字符串重写所有文件系统操作：([2](https://github.com/255doesnotexist/lintestor/commit/71851fef63f363655910e72252f7a94038e61c19), [3](https://github.com/255doesnotexist/lintestor/commit/78f8ba5778d953fc73df3a6219229f9e6395d5a6))
- 使用 generics 重构 TOML 读取函数：[4](https://github.com/255doesnotexist/lintestor/commit/ad86d134b24de47c90e9a82e24fd4e78ee2f132e)
- bug fix: [1](https://github.com/255doesnotexist/lintestor/commit/b7d5f4815296bac8b745e41af8e3f4ef84e646d8), [2](https://github.com/255doesnotexist/lintestor/commit/d97d0bf00a2d7e89dbbf4e0343142cb9ec03958c), [3](https://github.com/255doesnotexist/lintestor/commit/78f8ba5778d953fc73df3a6219229f9e6395d5a6), [4](https://github.com/255doesnotexist/lintestor/commit/bc55b7a1872d95b24a005d1bd7d34f8a65c93ea4), [5](https://github.com/255doesnotexist/lintestor/commit/1c376106442daa26d01ba78622cff4a4353d2023), [6](https://github.com/255doesnotexist/lintestor/commit/7d5f3a73351cedf53dac3700bb31356776cfa266), [7](https://github.com/255doesnotexist/lintestor/commit/1cf9b9133464eb7928f5ed550914d4931c2a597e)
- 其他数个 chores & linting commit

### 文档
继续维护和新增了数处usage和代码文档：([1](https://github.com/255doesnotexist/lintestor/commit/199a093d58e569f65eaae3d6a88124408f5e17f2), [2](https://github.com/255doesnotexist/lintestor/commit/4f115a7bc9607ae29391ca3e21f6ae9c459f3e34), [3](https://github.com/255doesnotexist/lintestor/commit/44f005cf33763cd920ee7f31ad86d04213ad0614), [4](https://github.com/255doesnotexist/lintestor/commit/8c037b2d5410a5f5bcc77c674bb41f93497b9239), [5](https://github.com/255doesnotexist/lintestor/commit/1c454929ee407a735d3ae0e0f6f6d7ce8a0a9aa3), [6](https://github.com/255doesnotexist/lintestor/commit/589c7f59f28cf128616633f5206d46ebd111c424))

### 协作
- 审核/合并了团队成员的数个PR: [#30](https://github.com/255doesnotexist/lintestor/pull/30), [#37](https://github.com/255doesnotexist/lintestor/pull/37), [#38](https://github.com/255doesnotexist/lintestor/pull/38)
- raised issue #29 & #34, closed #24 & #25 

## RuyiSDK 支持矩阵相关
帮助校对现有文档，补全了缺失的 Milk-V Jupiter 条目 和 LicheeRV Nano 条目中的错误：[PR](https://github.com/KevinMX/support-matrix/pull/43)

## 技术分享
10/30 下午进行了一次技术分享，谈 lintestor 遇到的主要技术问题和解决方案与心得体会：[slide](./lintestor_talk241030.pdf)

## 其他
- 向 mentor 申请一块 VisionFive 2, 自行研究在 Arch Linux RISC-V 上成功启动 X11 桌面（见 [week3](week3/week3.md) 周报）
- 尝试编译 [UniProton 的 Milk-V Duo 移植](https://github.com/openeuler-riscv/duo-buildroot-sdk) 但暂告失败 （见 [week3](week3/week3.md) 周报） 