# month1/week1
> delayed report covering 20241009-20241014

I contributed the following to the `lintestor` project:
- [feat: args to specify distros/packages to test](https://github.com/255doesnotexist/lintestor/commit/f78035383a71b031cc37de4eaa763882e524cf4e): 
- [feat: auto-detect distros and packages (#29)](https://github.com/255doesnotexist/lintestor/commit/acf634fd2c59859ca5cf3fc31cc3e63256258526): Replaced the old approach of root configurations with automatic discovery of test folders (distros and packages folder).
  - Made some major refactor efforts in the process, e.g. [fix(all): use PathBuf for all local filesystem operations](https://github.com/255doesnotexist/lintestor/commit/71851fef63f363655910e72252f7a94038e61c19): Rewrite every local filesystem operations to use Rust's PathBuf for enhanced robustness
- [refactor(config): generic config toml reader](https://github.com/255doesnotexist/lintestor/commit/ad86d134b24de47c90e9a82e24fd4e78ee2f132e): Introduced an universal config toml reader template to simplify the config serializing process, showcasing the use of Rust's generics.
- bug fixes, documentation and chores: 
  - [fix: add parameter in distro configs](https://github.com/255doesnotexist/lintestor/commit/b7d5f4815296bac8b745e41af8e3f4ef84e646d8)
  - [docs(usage): document distro and package flags](https://github.com/255doesnotexist/lintestor/commit/44f005cf33763cd920ee7f31ad86d04213ad0614)
  - [bump dependencies](https://github.com/255doesnotexist/lintestor/commit/daca50ce9dd8ea68576f58b5a14907f5d887d1fd)
- Reviewed PR from PangLARS: [#30](https://github.com/255doesnotexist/lintestor/pull/37)