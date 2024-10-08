# month1/week0
What I did this week, during holiday:
## `lintestor` development
### New Features
- Implemented "All tests failed" indicator (marked by ❌) in generated Markdown report ([commit](https://github.com/255doesnotexist/lintestor/commit/11236fb1c3c1a19f74ad98b58fd7825e00721ff7))
- Added a flag `--skip-successful` to skip all completed successful tests ([commit](https://github.com/255doesnotexist/lintestor/commit/f91085286b731514facb629cf33c189458ae0a9f))
### Bug fixes
- Fix `metadata.sh` being discovered as a test script ([commit](https://github.com/255doesnotexist/lintestor/commit/ebac3079d1bc5de7f5adec475939a4dd004f9798))

### Docs & Chores
- [docs: move prebuilt binary docs to readme](https://github.com/255doesnotexist/lintestor/commit/199a093d58e569f65eaae3d6a88124408f5e17f2)
- [docs(usage): skip-successful flag](https://github.com/255doesnotexist/lintestor/commit/4f115a7bc9607ae29391ca3e21f6ae9c459f3e34)
- [linting: make clippy happy](https://github.com/255doesnotexist/lintestor/commit/421eceb3c5f35332c8d16929dbc137d3aa979345)
- [chore(deps): bump clap from 4.5.18 to 4.5.19](https://github.com/255doesnotexist/lintestor/commit/a0eada0db76e9858e64302de6aa42f27bd34baca)

### Collaboration
- Closed issue [#25](https://github.com/255doesnotexist/lintestor/issues/25)

## RuyiSDK support matrix
More proofreading: [merged pull request](https://github.com/KevinMX/support-matrix/pull/43)
- Add missing Milk-V Jupiter entry in support matrix
- Fix incorrect "Duo 256M" info in LicheeRV Nano's docs


## Future plans
- rewrite Markdown generation process (perhaps with a third-party crate) and implement skipping of designated tests in `lintestor`