# month2
产出记录: 20241031-20241129

周报（英文）：[week0](week0/week0.md) / [week1](week1/week1.md) / [week2](week2/week2.md) / [week3](week3/week3.md) / [week4](week4/week4.md)

## 软件包自动化测试工具 lintestor

> 因开发基本完成且本月有优先级更高的任务，开发暂时停滞
- [chores: bump version](https://github.com/255doesnotexist/lintestor/commit/41fb72f89a21415653d8141cd357fb631d920bc0)
- 讨论关于稳定版本的 [roadmap](https://github.com/255doesnotexist/lintestor/issues/40)

## RuyiSDK 支持矩阵相关

进行了 Milk-V Duo / Duo 256M 在 8 个发行版/RTOS 上的可用性测试，共新撰写 8 篇报告，更新 6 篇报告：

### PRs 
- [duo/duo256m: Add/Update RT-Thread/RT-Smart](https://github.com/ruyisdk/support-matrix/pull/97)
- [duo/duo256m: Update Alpine/FreeRTOS/openEuler/Fedora/Ubuntu](https://github.com/ruyisdk/support-matrix/pull/99)
- [duo/duo256m: Update Yocto](https://github.com/ruyisdk/support-matrix/pull/106)
- [duo256m: Update Alpine & RT-Thread Smart](https://github.com/ruyisdk/support-matrix/pull/109)

### 内容详细

**新增**测试报告：
- RT-Thread Smart @ Duo256M
- RT-Thread @ Duo
- Fedora @ Duo256M
- Alpine Linux @ Duo (twice)
- Ubuntu @ Duo
- Ubuntu @ Duo256M
- Yocto @ Duo
- Yocto @ Duo256M

**更新**测试报告：
- RT-Thread Smart @ Duo
- RT-Thread Smart @ Duo256M
- RT-Thread @ Duo256M
- Alpine Linux @ Duo256M (twice)
- FreeRTOS @ Duo
- openEuler @ Duo

## 测试报告任务

### RT-Thread 测试相关

除上文 OS 可用性测试报告外， 还主导进行了 RT-Thread 在 Duo/Duo256M 上的常见 benchmark 工具调研和测试：[7 commits in repo](https://github.com/QA-Team-lo/rttest/commits/main/)
- 进行了 Coremark, dhrystone, anv_bench 的测试
  - 对于 Coremark，自行 patch 了相关代码使其能够编译运行
- 校对，优化排版，润色和书面化 LaTeX 测试报告：[pdf artifact](https://github.com/QA-Team-lo/rttest/blob/main/Duo_RTT_Report.pdf)

## 浏览器/数据库测试相关
- 校对，优化排版，润色和书面化 Firefox 测试报告：[pdf artifact](https://github.com/QA-Team-lo/firefox_test/blob/main/report/main.pdf)
  - 试用 LPi4A 远程 VNC 进行了少量手动测试，但因过于卡顿而放弃
- 校对，优化排版，润色和书面化 Chromium 测试报告：[pdf artifact](https://github.com/QA-Team-lo/chromium_test/blob/main/report/main.pdf)

## 玄铁课程视频任务

共观看并评论 15 个视频，相关评论内容等见组内共享文档

## 其他
- 将 RT-Thread / Firefox 的测试报告仓库 License 修改为 Apache 2.0：([commit](https://github.com/QA-Team-lo/rttest/commit/eda389e231f797f7f2f2b4d61ed0ab4cb655d14d), [commit](https://github.com/QA-Team-lo/firefox_test/commit/d6474a9483bfbd8b28602d4c69728246f9997f09))
- 通过定位原仓库编译错误并修改 device tree patch 的方式成功运行上文所述的 Yocto：[external PR](https://github.com/kinsamanka/meta-milkv/pull/8)

