# week0/testround
> still in the [mentor pick] stage.

Environment provided: remote access to a Milk-V Duo S, connected to a Debian VM through [Badgerd SDWireC](https://badgerd.nl/sdwirec/) (thanks a lot!)

## task1: Board preparation; Debian image flashing test with `boardtest`

The board is connected to the host on `ttyUSB0`, with the SDWireC serial being `sdwirec_alpha` (visible through `sudo sd-mux-ctrl --list`) and the SD card device at `/dev/sda`.

Flash [Fishwaldo's sophgo-sg200x-debian](https://github.com/Fishwaldo/sophgo-sg200x-debian) image. Run `sudo sd-mux-ctrl --device-serial=sdwirec_alpha --dut` to bring up the SD card connection (?), power up the board, then access the system through serial tty via `minicom` with baud rate `115200`.

Image flashing and simple environment testing could be done with [boardtest](https://github.com/255doesnotexist/boardtest). I've added support for Milk-V Duo S and Debian to the project in [this PR](https://github.com/255doesnotexist/boardtest/pull/1/). Here's my example run:
```
(pyenv) aisuneko@Photon:~/boardtest$ python main.py -s -f -b boards/milkv_duo_s_config.toml

          Serial: sdwirec_alpha
          Board config: boards/milkv_duo_s_config.toml
          Flashing: True
          Testing: True
          Stdout log: True

==================================================
Running test suite for OS: Debian...
==================================================

Preparing to flash OS Debian...
Do you want to continue with flashing the OS image?  [y/n] (n): y
Connecting SD card to test server for OS Debian flashing...
Executing command: sudo sd-mux-ctrl --ts --device-serial=sdwirec_alpha
Connecting SD card to TS with serial sdwirec_alpha:
Connected to TS successfully.
Executing command: sudo dd if=/home/aisuneko/duos_sd.img of=/dev/sda bs=4M status=progress
Press Enter to confirm and continue...
935329792 bytes (935 MB, 892 MiB) copied, 41 s, 22.8 MB/s
223+1 records in
223+1 records out
935453184 bytes (935 MB, 892 MiB) copied, 64.4394 s, 14.5 MB/s
Connecting SD card to device under test for OS Debian...
Executing command: sudo sd-mux-ctrl --dut --device-serial=sdwirec_alpha
Connecting SD card to DUT with serial sfiles
Linux duos 5.10.4-20240527-2+ #1 Sat Jun 1 14:15:39 UTC 2024 riscv64

The programs included with the Debian GNU/Linux system are free software;
the exact distribution terms for each program are described in the
individual files in /usr/share/doc/*/copyright.

Debian GNU/Linux comes with ABSOLUTELY NO WARRANTY, to the extent
permitted by applicable law.
Linux duos 5.10.4-20240527-2+ #1 Sat Jun 1 14:15:39 UTC 2024 riscv64 GNU/Linux
PRETTY_NAME="Debian GNU/Linux trixie/sid"
NAME="Debian GNU/Linux"
VERSION_CODENAME=trixie
ID=debian
HOME_URL="https://www.debian.org/"
SUPPORT_URL="https://www.debian.org/support"
BUG_REPORT_URL="https://bugs.debian.org/"
processor       : 0
hart            : 0
isa             : rv64imafdvcsu
mmu             : sv39

Stopping test framework...


Test report generated: report.txt
```
## task2: Software/toolchain availability test with `lintestor`
[lintestor](https://github.com/255doesnotexist/lintestor) is a novel software availability testing framework written in Rust; it is perhaps one of the first such frameworks out there. Unfortunately, I've encountered several major usability issues during test runs, and spent quite some time this week fixing bugs and enhancing its functionalities.

Notable issues include:
- each package's report.json is generated directly within their respective test scripts; thus the json format might be inconsistent (which might disrupt the aggregating process) and causes severe redundancy in the test scripts
- not enough consideration of package dependencies in the package test files (thus tests often fail due to missing packages)
- no unified and concrete standard for writing test scripts
- testing artifacts might cause noticable litter in the target environment's filesystem
- On debian, `apt` might disrupt automatic package installation with interactive prompts; consider using `DEBIAN_FRONTEND=noninteractive` (see https://askubuntu.com/questions/972516/debian-frontend-environment-variable)
- no visible output from the test scripts
- SSH is the only supported connection method at the moment
- requires QEMU/SSH at all times (there was a `--locally` option but it appears to be broken)

I made the following changes to the project as of now ([here](https://github.com/aisuneko/lintestor), PR not submitted yet):
- Fixed the `--locally` flag to allow the program to run directly on the target environment (without going through SSH or QEMU)
- Added the `--verbose` flag to print all stdout from test scripts
- Did a major overhaul of the report generation process; this is now done entirely within the framework itself rather than from the individual test scripts
- Edited the test scripts for each implemented package to adapt to the changes above
- Refactored TestRunner and several other parts of code; plus various bug fixes and stability improvements

Some of my ideas for further enhancement (will discuss later with the author):
- Add support for serial connections
- Add support for multiple test scripts for each package
- Come up with a more stable convention for writing test scripts; Conduct thorough testing to increase robustness

## task3: Run a Docker/moby container on the board, eg. hello-world

`apt install docker.io && docker pull hello-world && docker run -it hello-world` should work... right?
```
docker: Error response from daemon: failed to create endpoint <endpoint> on network bridge:
        failed to add the host (veth<hash>) <=> sandbox (veth<hash>) pair interfaces:
        operation not supported
```
This happens whenever I try to run a container and there isn't much useful info to that on the web. Running it again with `--network=host` does return something interesting:
```
docker: Error response from daemon: failed to create shim task: OCI runtime create failed: runc create failed: unable to start container process: error during container init: error setting cgroup config for procHooks process: bpf_prog_query(BPF_CGROUP_DEVICE) failed: invalid argument: unknown.
```
According to https://github.com/docker/cli/issues/4273, this is likely due to the running kernel missing BPF/cgroupv2 related features. But the kernel in our Debian image is at 5.10, which is supposed to support cgroupv2 already (since 4.15)...

We could check whether our kernel meets the requirements to run Docker/moby with https://github.com/moby/moby/blob/master/contrib/check-config.sh:
```
info: reading kernel config from /proc/config.gz ...

Generally Necessary:
- cgroup hierarchy: cgroupv2
  Controllers:
  - cpu: available
  - cpuset: missing
  - io: available
  - memory: available
  - pids: available
- CONFIG_NAMESPACES: enabled
- CONFIG_NET_NS: enabled
- CONFIG_PID_NS: enabled
- CONFIG_IPC_NS: enabled
- CONFIG_UTS_NS: enabled
- CONFIG_CGROUPS: enabled
- CONFIG_CGROUP_CPUACCT: missing //!
- CONFIG_CGROUP_DEVICE: enabled
- CONFIG_CGROUP_FREEZER: missing //!
- CONFIG_CGROUP_SCHED: enabled
- CONFIG_CPUSETS: missing //!
- CONFIG_MEMCG: enabled
- CONFIG_KEYS: enabled
- CONFIG_VETH: missing //!
- CONFIG_BRIDGE: enabled
- CONFIG_BRIDGE_NETFILTER: enabled (as module)
- CONFIG_IP_NF_FILTER: enabled
- CONFIG_IP_NF_MANGLE: enabled
- CONFIG_IP_NF_TARGET_MASQUERADE: enabled
- CONFIG_NETFILTER_XT_MATCH_ADDRTYPE: enabled (as module)
- CONFIG_NETFILTER_XT_MATCH_CONNTRACK: enabled (as module)
- CONFIG_NETFILTER_XT_MATCH_IPVS: missing //!
- CONFIG_NETFILTER_XT_MARK: enabled (as module)
- CONFIG_IP_NF_NAT: enabled
- CONFIG_NF_NAT: enabled
- CONFIG_POSIX_MQUEUE: enabled
- CONFIG_CGROUP_BPF: missing //!

Optional Features:
...
```
Turns out that certain cgroup/BPF/veth related flags are indeed missing. We have to rebuild the kernel with them enabled:
1. We'll use the build scripts provided in https://github.com/Fishwaldo/sophgo-sg200x-debian. Clone the repo and append the following to `configs/duos/linux/defconfig`:
```
CONFIG_CGROUP_CPUACCT=y
CONFIG_CGROUP_FREEZER=y
CONFIG_CPUSETS=y
CONFIG_VETH=y
CONFIG_CGROUP_BPF=y
CONFIG_NETFILTER_XT_MATCH_IPVS=m
```
2. Generate Dockerfile with ./build_docker.sh
3. `docker run --privileged -it --rm -v ./configs/:/configs -v ./image:/output ghcr.io/fishwaldo/sophgo-sg200x-debian:master make BOARD=duos linux`; this will generate the deb packages `linux-headers`, `linux-image-duos` and `linux-libc-dev` under `./image/`
4. Upload these three packages to the board and install them (on top of existing ones) with `dpkg -i`
5.  reboot and select the newly built kernel entry in U-Boot and Voilà! 

Docker containers should be able to run at this point:

~~(running `check-config.sh` again shows that `CONFIG_CPUSETS` and `CONFIG_NETFILTER_XT_MATCH_IPVS` are still missing; I'm not sure why)~~

## sidenote
The SD cards loaded on the SDWireC dongle failed three times in a row; at least two of them got wasted due to some random filesystem corruption, which disrupted my work in the first few days. Is it a known compatibility issue with SDWireC?
