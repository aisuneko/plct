# week4 (month0/week3)
What I did this week:
## `lintestor` development
### Bug fixes
-  [fix: wrong remote connection display](https://github.com/255doesnotexist/lintestor/commit/9e7791e8082ea6027300387eaff1b1167022b561)
-  [fix(testscript_manager): error handling on missing metadata file](https://github.com/255doesnotexist/lintestor/commit/7020cd57a84ac2ed3e49aaf7ad3558401f34d837): Resolves issue [#20](https://github.com/255doesnotexist/lintestor/issues/20)
### Documentation & Chores
- [docs(usage): document nightly builds](https://github.com/255doesnotexist/lintestor/commit/80dbf70c5b2c2ea3c704a806b72e1d05344ee1ec), [docs(usage): re-add missing param](https://github.com/255doesnotexist/lintestor/commit/5d7fb9f1f998a0eb6c6f320e389251c4fcf68082): Add documentation for nightly builds and the `--cleanup` parameter
- [linting: make clippy happy](https://github.com/255doesnotexist/lintestor/commit/573aee80cf2868d8c2b05eb14ec475497cdd487d)
### Collaboration
- Fixed and closed issues #20, [#21](https://github.com/255doesnotexist/lintestor/issues/21); Suggested the addition of riscv64gc nightly builds

## RuyiSDK support matrix
### Documentation
merged PR: [Proofread and correct existing board entries and support matrix](https://github.com/KevinMX/support-matrix/pull/37)
  
  Helped revise and correct existing support matrix table and documentation. Changes include:
  - Added missing OS version information in the READMEs of certain boards
  - Proofread of the current support matrix:
    - Corrected support status of certain boards
    - Spotted two boards (CM32M433R, R128-EVT) which were tested but not present in the table
    - Added the missing "Yocto" (Xuantie Yocto Linux) column to the "Linux Distributions" section
    - Various other corrections (in [another merged PR](https://github.com/KevinMX/support-matrix/pull/39))

### Board testing
opened PR: [board/Duo256M: Add Alpine Linux](https://github.com/KevinMX/support-matrix/pull/42)
  - Successfully booted Alpine Linux on Milk-V Duo 256M using BSP kernel with modified Alpine riscv64 minirootfs
  - Wrote detailed test reports documenting the porting process, though no prebuilt images are available at the moment.

## Future plans
- Develop more features and squash more bugs for lintestor
- Try to package the above Alpine rootfs into a bootable image
  - If possible, help to initiate testing work of Alpine Linux for riscv64 platforms
- Get a demo running