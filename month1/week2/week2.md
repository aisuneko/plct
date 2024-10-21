# month1/week2
> covering 20241015-20241021
> 
I contributed the following to the `lintestor` project:

## New feature
### Parameter shorthands
Commit: [feat: add shorthand for parameters (#29)](https://github.com/255doesnotexist/lintestor/commit/3a7e0ba95dfbfe1fba9619c16a43f2670143de05)

You can now invoke the program with simplified parameters. 

e.g. `./lintestor --test --aggr --summ` can now be shortened to `./lintestor -tas`

### Integration test
PR: [testing: add integration test](https://github.com/255doesnotexist/lintestor/pull/33)

An experimental integration test of the project is finally available through `cargo test`. The test mimics a manual run of `./lintestor -tas` with example dummy test files included.
- [testing: add code for integration test](https://github.com/255doesnotexist/lintestor/commit/7841df9844345fb23797711e43252e96812fb38b)
- [testing: add test files for integration test](https://github.com/255doesnotexist/lintestor/commit/f0e389fb97ba76cd4143243388b778b394feb9da)
- [chores: move assert_cmd to dev-dependencies](https://github.com/255doesnotexist/lintestor/commit/3cf345569748bad0a6590d2a449d0a226c2dcdc0)
- [fix: remove connection info from test file configs](https://github.com/255doesnotexist/lintestor/commit/a3d2f9616abd23fdf04f3b40fcd667024755e0d4)

## Bug fixes
- [fix: alt approach of setting env_logger default level](https://github.com/255doesnotexist/lintestor/commit/d97d0bf00a2d7e89dbbf4e0343142cb9ec03958c): This is to address std::env::set_var being unsafe since Rust edition 2024
- [fix: use Path for all dir parameters](https://github.com/255doesnotexist/lintestor/commit/78f8ba5778d953fc73df3a6219229f9e6395d5a6): Rewrite every local filesystem operations to use Rust's Path instead of PathBuf (since the latter is an owned type)
- [fix: wrong reports.json path in aggregator](https://github.com/255doesnotexist/lintestor/commit/bc55b7a1872d95b24a005d1bd7d34f8a65c93ea4)
## Documentation
- [docs: update usage and readme](https://github.com/255doesnotexist/lintestor/commit/8c037b2d5410a5f5bcc77c674bb41f93497b9239)
- [docs(utils): add documentation for new utils functions](https://github.com/255doesnotexist/lintestor/commit/1c454929ee407a735d3ae0e0f6f6d7ce8a0a9aa3)
- [docs(usage): document parameter shorthands](https://github.com/255doesnotexist/lintestor/commit/589c7f59f28cf128616633f5206d46ebd111c424)
## Collaboration
- Found and raised issue [#34](https://github.com/255doesnotexist/lintestor/issues/34) regarding serde macros, which was later fixed
- Closed [#24](https://github.com/255doesnotexist/lintestor/issues/34)
- Reviewed PR from PangLARS: [#37](https://github.com/255doesnotexist/lintestor/pull/37)
- Bump dependencies (PR [#35](https://github.com/255doesnotexist/lintestor/pull/35), [#36](https://github.com/255doesnotexist/lintestor/pull/36))