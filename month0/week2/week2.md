# week2 (month0/week1)

What I did this week:
- [Fixed an output bug](https://github.com/255doesnotexist/lintestor/commit/ce21f2e7c21ad6e5c155c5e61b72cfbc613a0087) in [lintestor](https://github.com/255doesnotexist/lintestor/)
- My Milk-V Duo 256M board arrived at Wednesday (9/11). Did my first demo (Image Classification with MobileNet-Caffe) and wrote the report. See the doc [here](demo_duo256_mobilenet.md).
  - This also corresponds to a task on the QA team's internal kanban which I claimed. Will submit my outputs there after one more demo (I think)

## Plans for next week
- The demo above is fairly simple, so for the next project I would try running small language models on the board, similar to [this demo](https://github.com/255doesnotexist/bpi-f3_demos/blob/main/qwen2.md). Due to its tight memory constraint (256M), I'm still looking for models of interest with <200M parameters...
- Investigate on possible implementations of package metadata in `lintestor` as discussed in issues [#6](https://github.com/255doesnotexist/lintestor/issues/6) and [#8](https://github.com/255doesnotexist/lintestor/issues/8). Doing so might involve reworking the command execution logic with the [rexpect](https://github.com/rust-cli/rexpect) crate, since the current `std::process::Command` implementation seems to be quite limited. 
- After that, re-run a `lintestor` test on Milk-V Duo S (the one provided by my mentor during the pretask, if still available).