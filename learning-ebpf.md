[Learning eBPF](https://learning-oreilly-com.ezproxy.spl.org/library/view/learning-ebpf/9781098135119/)
- [video: History of eBPF](https://youtu.be/DAvZH13725I)
- [video: eBPF and Kubernetes](https://youtu.be/99jUcLt3rSk)
- [unofficial eBPF Spec](https://oreil.ly/FXcPu) (with list of valid instructions)
- BTF: BPF Type Format
- LSM: Linux Security Module
- XDP: eXpress Data Path

***
-- bpftool [libbpf/bpftool](https://github.com/libbpf/bpftool)
		- git clone --recurse-submodules https://github.com/libbpf/bpftool.git
		- git submodule update --init
		- cd src && make && sudo make install
	- bpftool prog load <object file> <device file> (path: '/sys/fs/bpf/<name of program>')
	- bpftool prog list
	- bpftool prog show id <id> [--pretty]
	- bpftool prog show name <name>
	- bpftool prog show tag <tag>
	- bpftool prog show pinned <device file>
	- bpftool prog dump xlated name <name>
	- bpftool prog dump jited name <name> 
	- bpftool prog show name hello - after removing <device file>
- Check architecture
	- dpkg --print-architecture
		- incase of my M2 it is "arm64"
- Running eBPF programs on Docker containers
	- https://andreybleme.com/2022-05-22/running-ebpf-programs-on-docker-containers/
		- Dockerfile: Dockerfile.ebs-programs.ubuntu
			- docker build . -f Dockerfile.ebs-programs.ubuntu -t ebpf-programs:1.0.0
			- docker run -d ebpf-programs:1.0.0 - [displays <target>]
			- docker ps - [copy <target>]
			- docker exec -t <target> /bin/bash
		- to mount 'debugfs', need to execute in privileged mode and then mount 'debugfs'
			- docker run --privileged -d ebpf-programs:1.0.0
			- mount -t debugfs none /sys/kernel/debug
		- CONFIG_IKHEADERS not set to "y"
	- https://petermalmgren.com/docker-mac-bpf-perf/

***
- Install Linux Kernel
    - https://phoenixnap.com/kb/build-linux-kernel

***
- Disks and File Systems with eBPF
    - https://blog.netdata.cloud/how-to-monitor-your-disks-and-filesystems-now-also-with-ebpf/
- Running eBPF Programs on Docker Containers
	- https://andreybleme.com/2022-05-22/running-ebpf-programs-on-docker-containers/
