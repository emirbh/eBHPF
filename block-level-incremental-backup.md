# Block Level Incremental Backup (BLIB)

The of the module is to show how changes in the file sysrem are being translated into disk blocks. The solution based on the filter driver was implemented in late 1990's for NTFS nd VxFS on SUN Solaris and NTFS, this version BLIB relies solely on Extended Berkeley Packet Filter - [eBPF](https://ebpf.io/).

## Invstigation