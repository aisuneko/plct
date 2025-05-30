# month8
产出记录：20250430-20250530

## RuyiSDK 支持矩阵相关

### PRs
[Add Pine64 Ox64](https://github.com/ruyisdk/support-matrix/pull/293)
[Update RV-STAR](https://github.com/ruyisdk/support-matrix/pull/294)
[Update Pine64 Oz64/Star64/Pinecone](https://github.com/ruyisdk/support-matrix/pull/307)

### 报告详细

主要内容为测试上月自费购入的 Pine64 系列开发板 (Ox64/Oz64/Star64/Pinecone)，以及新申请的开发板（RV-STAR/DongshanPI-D1s/MangoPI MQ）。

新增 16 篇：
- Buildroot @ Ox64
- Arch Linux @ Ox64
- NuttX @ Ox64
- FreeRTOS @ RV-STAR
- RT-Thread @ RV-STAR
- ThreadX @ RV-STAR
- uCOSII @ RV-STAR
- LiteOS @ RV-STAR
- Debian @ Oz64
- NuttX @ Oz64
- Ubuntu @ Star64
- Armbian @ Star64 (CFH)
- ArchLinux @ Star64 (CFH)
- Yocto @ Star64 (CFH)
- NixOS @ Star64 (CFH)
- NuttX @ Pinecone

更新 2 篇：
- NuttX @ DuoS
- Debian @ LicheeRV Nano

尚未撰写报告：

- Melis @ DongshanPI-D1s
- MangoPI MQ
- DietPi @ Star64 (CFH)

## lintestor

响应 @255doesnotexist 正在进行中的新版本开发，进行了一次[大型 code review](https://github.com/255doesnotexist/lintestor/pull/96), 以及大量的重构和代码优化工作：
- [refactor: remove obsolete code and re-enable integration test](https://github.com/255doesnotexist/lintestor/pull/96/commits/72b11e546cae412adda52c9ad445ffbc1b9d31b2)
- [refactor: remove obsolete code and unused imports](https://github.com/255doesnotexist/lintestor/pull/96/commits/ad89ca0d090736899ab51ca86442a86078bc95e0)
- [refactor: remove unused summary and aggregation](https://github.com/255doesnotexist/lintestor/pull/96/commits/14fa0f8277c1fe179f2a3084a954aa429bfb3f25)
- [refactor: fill in error handling for template functions](https://github.com/255doesnotexist/lintestor/pull/96/commits/f49211133ce457539bd97c9ce99982be392ec7e6)
- [refactor: remove useless functions](https://github.com/255doesnotexist/lintestor/pull/96/commits/75b17b464d70dd20455edffc7fb02c6808473dd6)
- [refactor: make clippy happy](https://github.com/255doesnotexist/lintestor/pull/96/commits/818c17ebeed0a85fa143ddf7e431f3822f0f41ae)
- [refactor(connection/ssh): use Default for param initialization](https://github.com/255doesnotexist/lintestor/pull/96/commits/ef05b23d76333122be013f380503da52de5e3e80)

## 其他
为 Pine64 Oz64 绘制了一幅板载引脚 pinout 图：https://wiki.pine64.org/wiki/File:Oz64_Board_pinout_by_aisuneko.png

## 下月计划（暂定）
- 补完先前所有已测试但尚未撰写的报告
- 对已有开发板剩余可能尚未测试的项目查漏补缺
- 继续 lintestor 开发